---
title: HDS Testing Page
deprecated: false
hidden: false
icon: far fa-arrows-maximize
metadata:
  robots: index
---
<br />

## h2

<Callout icon="📘" theme="info">
  Note

  The member elements of the `routingParameters` object literal directly map to the URL parameters required by the HERE Routing API. The parameter object can include any parameters recognized by the Routing API, offering complete flexibility in defining a route calculation request.
  Based on configuration from the preceding example, the following routing request is formed:

  ```http
  https://router.hereapi.com/v8/routes
  ?apikey={YOUR_API_KEY}
  &routingMode=fast
  &transportMode=car
  &origin=56.97,24.09
  &destination=54.70,25.24
  &return=polyline
  ```

  For more information, see [Calculate route](/routing/docs/) in the HERE Routing API v8 Developer Guide.
</Callout>

**Result**: The following map shows the result of the route calculation, with the start of the Route in Vilnius, Lithuania, and end of the route in Riga, Latvia, indicated by markers with default icons, and the route itself shown as a blue polyline:
![The map after calculating the route](https://files.readme.io/38403a494c5900dd8b2f4f5dcfedeaf4b784c964139b928021249fc9eaaecb5b-routing-simple.png)

## Add multiple waypoints

Using waypoint markers in route planning and navigation applications can help users visualize and understand their route more effectively. Such markers provide clear indications of where the route passes through or stops at specific points of interest.

The following steps provide instructions on how to add waypoint markers, based on the preceding routing example:

1. Add the waypoints object with the coordinates specifying the placement of additional markers on the map:

   ```javascript
   const waypoints = [
     // Liepaja, Latvia
     { lat: 56.5, lng: 21.01 },
     // Klajpeda, Lithuania
     { lat: 55.7, lng: 21.2 },
   ];
   ```

2. Create an empty array to store waypoint markers:

   ```javascript
   const waypointMarkers = [];
   ```

3. Update the HERE Routing API v8 query to include [via waypoints](/routing/docs/via), with coordinates defined by the waypoints variable:

   ```javascript
   const routingParameters = {
     routingMode: "fast",
     transportMode: "car",
     origin: `${origin.lat},${origin.lng}`,
     destination: `${destination.lat},${destination.lng}`,
     return: "polyline",
     // Add a via parameter to the query for each coordinate pair:
     via: new H.service.Url.MultiValueQueryParameter(
       waypoints.map((wp) => `${wp.lat},${wp.lng}`)
     ),
   };
   ```

4. Within the `onResult` callback function, add markers for each waypoint and add them to the map:

   ```javascript
   // Create waypoint markers:
   waypoints.forEach((waypoint) => {
     const waypointMarker = new H.map.Marker({
       lat: waypoint.lat,
       lng: waypoint.lng,
     });
     // Populate the waypointMarkers array:
     waypointMarkers.push(waypointMarker);
   });
   ```

5. Add waypoint markers to the map objects group:

   ```javascript
   // Add ...waypointMarkers as an argument:
   group.addObjects([routeLine, startMarker, endMarker, ...waypointMarkers]);
   ```

   **Result**: The map now displays waypoint markers together with an updated route that passes through the `via` waypoints:
   ![Route that includes via waypoints](https://files.readme.io/53e4bbbd8ebecf92099a2a686aae464cb7e2170d931441bcea1ed5fae6458990-routing-waypoints.png)

## Customize marker style

In the HERE Maps API for JavaScript, you can use custom markers instead of the pre-defined marker icons. For example, you can use custom SVG styles that allow you to create markers with unique and distinctive appearances. This can be particularly useful when you want to match the markers to your brand or design requirements or make it easier for user to distinguish between various marker types (for example, start, stop, or waypoint).

1. Define the style for marker icons:

   ```javascript
   // Define the marker style
   const commonSvgStyle = (
     fill
   ) => `<svg xmlns="http://www.w3.org/2000/svg" width="48" height="48" viewBox="0 0 48 48">
       <path d="M24 0C12.955 0 4 9.075 4 20.075C4 28.35 24 48 24 48S44 28.35 44 20.075C44 9.075 35.045 0 24 0Z" fill="${fill}"/>
   </svg>`;

   // Define the fill colors for start, end, and waypoint markers:
   const startFill = "red";
   const endFill = "green";
   const waypointFill = "purple";

   // Create SVG icons for start, end, and waypoint markers using the common style and the corresponding fill color:
   const startIconSvg = commonSvgStyle(startFill);
   const endIconSvg = commonSvgStyle(endFill);
   const waypointIconSvg = commonSvgStyle(waypointFill);
   ```

2. Within the `onResult` callback function, update the `startMarker`, `endMarker`, and `waypointMarker` variables with the corresponding SVG style definition, as shown in the following example:

   ```javascript
   // Origin marker (red):
   const startMarker = new H.map.Marker(origin, {
     icon: new H.map.Icon(startIconSvg, {
       size: {
         w: 32,
         h: 32,
       },
     }),
   });

   // Destination marker (green):
   const endMarker = new H.map.Marker(destination, {
     icon: new H.map.Icon(endIconSvg, {
       size: {
         w: 32,
         h: 32,
       },
     }),
   });

   // Waypoint markers (purple):
   waypoints.forEach((waypoint) => {
     const waypointMarker = new H.map.Marker({ lat: waypoint.lat, lng: waypoint.lng},
     {
       icon: new H.map.Icon(waypointIconSvg, { size: { w: 24, h: 24 } })
     });
     waypointMarkers.push(waypointMarker);
   });
   ```

<Callout icon="📘" theme="info">
  Hint

  You can change the icon size through `w` (width) and `h` (height) parameters, for example, to make waypoint markers less prominent that the start and end markers.
</Callout>

**Result**: Each marker type now has a distinct style, as shown in the following figure:
![Route with customized markers](https://files.readme.io/4043e145a4db9828b7dbf16d2f91f527b3840a86d7e67c729ab322fe8bb592ea-routing-markers.png)

## Show route direction arrows

The HERE Maps API for JavaScript offers a way to render arrows on the route polyline to indicate the direction of travel. The following code enhances the `onResult` callback from the previous example by providing a style that describes the dash of the polyline through the [H.map.SpatialStyle](/maps-api-for-js/page/maps-api-for-javascript-api-reference-3-2-h-map-spatialstyle) class.

To render the route in the form of direction arrows, replace the existing `routeLine` definition with the following code:

```javascript
const routeLine = new H.map.Polyline(multiLineString, {
  style: {
    strokeColor: 'blue',
    lineWidth: 4,
    lineDash: [1.5, 0.3],
    lineDashImage: H.map.SpatialStyle.DashImage.ARROW
    },
});
```

**Result**: The following figure shows how route appears on the map:
![The map after adding a route line with arrows](https://files.readme.io/935039f668d57f067de9c9ff55ec0ffb500e149ef94a1cfeb81fab705a4b4b74-routing-arrows.png)

## Display isolines

An isoline is a line on a map that represents the area that one can reach from a specific point within a certain amount of time or distance based on a particular mode of transportation.

The following code sample shows how to calculate an isoline representing points that lie no further than a 15 minutes' car journey from the center of Riga. The example uses the [`RoutingService`](/maps-api-for-js/page/maps-api-for-javascript-api-reference-3-2-h-service-routingservice8) class to obtain the isoline and builds upon the base map described in [Get started with HERE Maps API for JavaScript](doc:quick-start) as the foundation for introducing code additions.

```javascript
var routingParams = {
  transportMode: "car",
  origin: "56.9,24.1",
  "range[values]": "900",
  "range[type]": "time",
  routingMode: "fast",
  optimizeFor: "quality",
};

// Define a callback function to process the isoline response.
var onResult = function (result) {
  var isolines = result.isolines[0],
    objects = [new H.map.Marker(result.departure.place.location)];

  isolines.polygons.forEach((section) => {
    let lineString = H.geo.LineString.fromFlexiblePolyline(section.outer);

    // Create a polygon to display the area
    objects.push(new H.map.Polygon(new H.geo.Polygon(lineString)));
  });

  // Add the polygon and marker to the map:
  map.addObjects(objects);

  // Center and zoom the map so that the whole isoline polygon is
  // in the viewport:
  map.getViewModel().setLookAtData({ bounds: objects[1].getBoundingBox() });
};

// Get an instance of the routing service:
var router = platform.getRoutingService(null, 8);

// Call the Routing API to calculate an isoline:
router.calculateIsoline(routingParams, onResult, function (error) {
  alert(error.message);
});
```

The code from the preceding example performs the following operations:

1. **Routing parameters**: Define a `routingParams` object that specifies that the fastest routes for a car are to calculate, set the starting point and the time.
2. **Routing callback function**: Define a callback to invoke when the results of the routing request become available. The callback function creates a polygon, using the points of the calculated isoline, adds the polygon and a marker at the center of the isoline polygon to the map, and sets the map view port so that the entire isoline is visible.
3. **Routing service initialization**: Instantiate the [Routing Service v8](/maps-api-for-js/page/maps-api-for-javascript-api-reference-3-2-h-service-routingservice8).
4. **Calculate and display the isoline**: Call the Routing Service method [`calculateIsoline()`](/maps-api-for-js/page/maps-api-for-javascript-api-reference-3-2-h-service-routingservice8#calculateIsoline) passing to it the parameter object and the success and error callbacks.

**Result**: The map now displays an isoline with the requested parameters, as shown in the following figure:
![The map after adding the isoline polygon](https://files.readme.io/3711446662a850d7b95eb21abb5cd461c7a59f50b5734238ede6a32a91a41f0a-routing-isoline.png)

## Determine a route with addresses as input

Some use cases might require that you determine routing coordinates by geocoding addresses first. The following code samples use the [Search Service](/maps-api-for-js/page/maps-api-for-javascript-api-reference-3-2-h-service-searchservice) to geocode addresses for the origin and destination points so that the Routing Service can calculate a pedestrian route between those points and display the resulting route on the map. The asynchronous nature of operations like geocoding and routing calculations is handled by using promises to ensure the code flows correctly.

The following code sample builds upon the base map described in [Get started with HERE Maps API for JavaScript](doc:quick-start) as the foundation for introducing code additions.

1. Connect the map to the Search Service as shown in the following example:

   ```javascript
   const searchService = platform.getSearchService();
   ```

2. Define the search queries for the origin and destination points:

   ```javascript
   const originAddress = "Sv. Pētera baznīca, Riga";
   const destinationAddress = "Doma Laukums";
   ```

3. Enable geocoding of addresses in an asynchronous manner by using the Search Service based on the [HERE Geocoding and Search API](/geocoding-and-search/docs/):

   ```javascript
   // Geocode an address using the search service:
   function geocodeAddress(address) {
     return new Promise((resolve, reject) => {
       searchService.geocode(
         {
           q: address,
         },
         (result) => {
           /*
               Access the geographic position information of
               the first (presumably most relevant) result
               obtained from the geocoding process:
               */
           const location = result.items[0].position;
           resolve(location);
         },
         (error) => {
           console.error(
             `Error fetching geocoding data for ${address}:`,
             error
           );
           reject(error);
         }
       );
     });
   }
   ```

   The `geocodeAddress()` function from the preceding example encapsulates the asynchronous geocoding call, allowing you to pass an address and receive a promise that resolves to an object containing the corresponding latitude and longitude upon successful geocoding, or rejects with an error if the geocoding fails. The function takes an `address` string as an argument to send a request to the HERE Geocoding and Search API v7, for example:

   ```http
   https://geocode.search.hereapi.com/v1/geocode?xnlp=CL_JSMv3.2.0.0&apikey={YOUR_HERE_APIKEY}&q=Sv.%20P%C4%93tera%20bazn%C4%ABca%2C%20Riga
   ```

   Assuming the geocoding operation was successful, the function extracts the value of the `position` attribute value from the most relevant result for the provided address query. For more information on the HERE Geocoding and Search API requests and responses, see [Get started](/geocoding-and-search/docs/) in the corresponding Developer Guide.

4. Use `Promise.all` to geocode both origin and destination addresses, as shown in the following example:

   ```javascript
   // Use Promise.all to geocode both origin and destination addresses
   Promise.all([geocodeAddress(originAddress), geocodeAddress(destinationAddress)])
       .then(([origin, destination]) => {
           // Create routing parameters for calculating the route
           const routingParameters = {
               routingMode: "fast",
               transportMode: "pedestrian",
               origin: `${origin.lat},${origin.lng}`,
               destination: `${destination.lat},${destination.lng}`,
               return: "polyline",
           };

           const onResult = function(result) {
               if (result.routes.length) {
                   const lineStrings = [];
                   result.routes[0].sections.forEach((section) => {
                       lineStrings.push(
                           H.geo.LineString.fromFlexiblePolyline(section.polyline)
                       );
                   });

                   const multiLineString = new H.geo.MultiLineString(lineStrings);
                   const routeLine = new H.map.Polyline(multiLineString, {
                       style: {
                           strokeColor: "blue",
                           lineWidth: 4,
                       },
                   });

                   const startMarker = new H.map.Marker(origin);
                   const endMarker = new H.map.Marker(destination);

                   const group = new H.map.Group();
                   group.addObjects([routeLine, startMarker, endMarker]);
                   map.addObject(group);

                   map.getViewModel().setLookAtData({
                       bounds: group.getBoundingBox(),
                   });
               }
           };

           const router = platform.getRoutingService(null, 8);

           router.calculateRoute(routingParameters, onResult, function(error) {
               alert(error.message);
           });
       })
       .catch((error) => {
           console.error("Error fetching coordinates:", error);
       });
   ```

   This method is calling `geocodeAddress()` twice, which returns promises for each geocoding operation. `Promise.all()` waits for both of these promises to resolve, allowing you to handle their combined results (the resolved values of both promises) in the `.then()` block.

The following figure illustrates the resulting map, which includes the origin and destination markers placed at the coordinates obtained through address geocoding, along with the calculated route between these markers:
![A map showing routing information between geocoded addresses](https://files.readme.io/3b553f14b5e36a7060ceeaf9b3a2ba374f91dd04d94f21e4025f8f010d39a2f5-routing-address.png)

## Next steps

* For more information about the HERE Routing API v8, see the [corresponding documentation](/routing/docs/).
* For more information about the HERE Geocoding and Search API v7, see the [corresponding documentation](/geocoding-and-search/docs/).
