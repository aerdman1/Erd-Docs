---
title: Context menu
deprecated: false
hidden: false
icon: fad fa-file-lines
metadata:
  robots: index
---
test

<HTMLBlock>{`
<div id="demo-map" data-demo-map style="height:480px;width:100%"></div>
`}</HTMLBlock>

```json
function showGeoJSONData(map) {
  // Create GeoJSON reader which will download the specified file.
  // Shape of the file was obtained by using HERE Geocoding and Search API.
  // It is possible to customize look and feel of the objects.

  var reader = new H.data.geojson.Reader(
    "https://heremaps.github.io/maps-api-for-javascript-examples/display-geojson-on-map/data/berlin.json",
    {
      // This function is called each time parser detects a new map object
      style: function (mapObject) {
        // Parsed geo objects could be styled using setStyle method
        if (mapObject instanceof H.map.Polygon) {
          mapObject.setStyle({
            fillColor: "rgba(255, 0, 0, 0.5)",
            strokeColor: "rgba(0, 0, 255, 0.2)",
            lineWidth: 3,
          });
        }
      },
    }
  );

  // Start parsing the file
  reader.parse();

  // Add layer which shows GeoJSON data on the map
  map.addLayer(reader.getLayer());
}

/**
 * Boilerplate map initialization code starts below:
 */
// Step 1: initialize communication with the platform
var platform = new H.service.Platform({
  apikey: "rVczblKDUJs-XSyUkLooaPkP4wcqHPaOB3oFvO1on3M",
});
var defaultLayers = platform.createDefaultLayers();

// Step 2: initialize a map
var map = new H.Map(
  document.getElementById("map"),
  defaultLayers.vector.normal.map,
  {
    zoom: 10,
    center: { lat: 52.522763341087874, lng: 13.492702024100026 },
    pixelRatio: window.devicePixelRatio || 1,
  }
);
// add a resize listener to make sure that the map occupies the whole container
window.addEventListener("resize", () => map.getViewPort().resize());

// Step 3: make the map interactive
// MapEvents enables the event system
// Behavior implements default interactions for pan/zoom (also on mobile touch environments)
var behavior = new H.mapevents.Behavior(new H.mapevents.MapEvents(map));

// Create the default UI components
var ui = H.ui.UI.createDefault(map, defaultLayers);

showGeoJSONData(map);
```
```html
<!DOCTYPE html>
<html>
  <head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=yes" >
    <meta http-equiv="Content-type" content="text/html;charset=UTF-8" >
    <meta name="description" content="Parse a GeoJSON file and display the data on a map" >
    <title>Display GeoJSON Data</title>
    <link rel="stylesheet" type="text/css" href="https://js.api.here.com/v3/3.1/mapsjs-ui.css" />
    <script type="text/javascript" src="https://js.api.here.com/v3/3.1/mapsjs-core.js"></script>
    <script type="text/javascript" src="https://js.api.here.com/v3/3.1/mapsjs-service.js"></script>
    <script type="text/javascript" src="https://js.api.here.com/v3/3.1/mapsjs-ui.js"></script>
    <script type="text/javascript" src="https://js.api.here.com/v3/3.1/mapsjs-mapevents.js"></script>
    <script type="text/javascript" src="https://js.api.here.com/v3/3.1/mapsjs-data.js"></script>
    <link rel="stylesheet" type="text/css" href="../template.css" />
    <link rel="stylesheet" type="text/css" href="demo.css" />
    <script type="text/javascript" src='../test-credentials.js'></script>
  <script>window.ENV_VARIABLE = 'developer.here.com'</script><script src='../iframeheight.js'></script></head>
  <body>
    <h1>Display GeoJSON Data</h1>
    <p>This example shows how to display objects from GeoJSON file on the map using built in parser.</p>
    <p>In order to work with GeoJSON files we have to additionally load data module of the API. Than we use H.data.geojson.Reader class, which downloads and parses the file. Than we add a layer on the map using addLayer method to see the results.</p>
    <div id="map"></div>
    <script type="text/javascript" src='demo.js'></script>
  </body>
</html>
```

<br />
