---
title: Welcome
deprecated: false
hidden: false
icon: far fa-calendar-circle-exclamation
metadata:
  robots: index
---
<br />



<Callout icon="📘" theme="info">
  Note

  The 3.1 version of this API has been deprecated. For continued support and feature development, upgrade to the latest [3.2 version](doc:introduction-maps-api-for-javascript).
</Callout>

[Angular](https://angular.io/) provides a set of powerful tools and features for building web applications. You can create an even more engaging experience for your users by combining these features with HERE SDKs and APIs.

For example, you can integrate HERE Maps with Angular to display interactive maps, geocode addresses, calculate routes, and more, all within the context of your Angular application.

See the following sections for step-by-step instructions on how to create a simple interactive map within the context of an Angular application.

## Before you begin

Sign up for a HERE developer account and obtain your API credentials. For more information, see [Get started](https://www.here.com/get-started).

## Install Angular CLI

Facilitate the development of a new Angular application by using the [Angular CLI](https://angular.io/cli).

1. In the Command Prompt, enter the following command to install Angular CLI:
   ```shell
   npm install -g @angular/cli
   ```

2. Initiate a new Angular project by entering the following command:
   ```shell
   ng new jsapi-angular && cd jsapi-angular
   ```

3. At the `Which stylesheet format would you like to use?` prompt, select the `CSS` option.

4. At the `Do you want to enable Server-Side Rendering (SSR) and Static Site Generation (SSG/Prerendering)?` prompt, press the `N` key, to disable server-side rendering and static site generation prerendering.

   **Result**: The system installs the required packages and creates a new `jsapi-angular` directory, with the Angular components residing in the `src` sub-directory. The `jsapi-angular` directory has the following structure:

   ```
   jsapi-angular
   ├── node_modules
   ├── package.json
   ├── .gitignore
   ├── .browserslistrc
   ├── .editorconfig
   ├── angular.json
   ├── karma.conf.js
   ├── README.md
   ├── tsconfig.app.json
   ├── tsconfig.json
   ├── tsconfig.spec.json
   ├── dist
   │   ├── ...
   └── src
       ├── app
       │   ├── app-routing.module.ts
       │   ├── app.component.css
       │   ├── app.component.html
       │   ├── app.component.spec.ts
       │   ├── app.component.ts
       │   └── app.module.ts
       ├── assets
       │   ├── ...
       ├── environments
       |   ├── ...
       ├── favicon.ico
       ├── index.html
       ├── main.ts
       ├── polyfills.ts
       ├── styles.css
       └── test.ts
   ```

5. In your project directory, install the `maps-api-for-javascript` NPM package which is hosted at [https://repo.platform.here.com/](https://repo.platform.here.com/) by adding a registry entry to the NPM configuration through the following command:
   ```shell
   npm config set @here:registry https://repo.platform.here.com/artifactory/api/npm/maps-api-for-javascript/
   ```

6. Install the package from the `@here` namespace by entering the following command:
   ```shell
   npm install @here/maps-api-for-javascript@1
   ```

7. Navigate to the `jsapi-angular` folder, and then open the `tsconfig.json` file in a preferred text editor.

8. In the `tsconfig.json` file, add the following setting under `angularCompilerOptions`:
   ```json
   "allowSyntheticDefaultImports": true
   ```

9. **Optional**: To verify that you completed the setup successfully, perform the following actions:
   1. Enter the following command:
      ```shell
      ng serve
      ```
      **Result**: This command launches a development server with the "hot reload" functionality.

   2. Initiate the Angular application by navigating to the `http://localhost:4200/` address in the browser.

      **Result**: The browser displays the Angular welcome   screen with the `Congratulations! Your app is running.` message.

      > #### Tip
      >
      > For Windows operating systems, to terminate the `ng serve` process, press `q + Enter`.

## Add a static map component

In your Angular application, generate a static map by creating a component that contains an `H.Map` namespace instance. This component renders the map through the corresponding container.

1. In the Angular CLI, generate the jsmap component by entering the following command:
   ```shell
   ng generate component jsmap
   ```
   **Result**: The command creates a `jsmap` folder in the `src/app` directory. The folder contains all the files required to build the component:
   ```
   └── src
       ├── app
       │   ├── jsmap
       |   |   ├── jsmap.component.css
       |   |   ├── jsmap.component.html
       |   |   ├── jsmap.component.spec.ts
       |   |   └── jsmap.component.ts
       │   ├── app-routing.module.ts
       │   ├── app.component.css
       │   ├── app.component.html
       │   ├── app.component.spec.ts
       │   ├── app.component.ts
       │   └── app.module.ts
       ...
   ```

2. Navigate to the `jsapi-angular/src/app/jsmap` directory, and then open the `jsmap.component.ts` file.

3. In the `jsmap.component.ts` file, replace the default code with the following code:

   ```javascript
   import { Component, ViewChild, ElementRef } from '@angular/core';
   import '@here/maps-api-for-javascript';

   @Component({
     selector: 'app-jsmap',
     standalone: true,
     templateUrl: './jsmap.component.html',
     styleUrls: ['./jsmap.component.css']
   })
   export class JsmapComponent {

     private map?: H.Map;

     @ViewChild('map') mapDiv?: ElementRef;

     ngAfterViewInit(): void {
       if (!this.map && this.mapDiv) {
         // Instantiate a platform, default layers and a map as usual.
         const platform = new H.service.Platform({
           apikey: '{YOUR_API_KEY}'
         });
         const layers = platform.createDefaultLayers();
         const map = new H.Map(
           this.mapDiv.nativeElement,
           // Add type assertion to the layers object...
           // ...to avoid any Type errors during compilation.
           (layers as any).vector.normal.map,
           {
             pixelRatio: window.devicePixelRatio,
             center: {lat: 52.5, lng: 13.4},
             zoom: 13,
           },
         );
         this.map = map;
       }
     }
   }
   ```

   This code imports the HERE Maps API for JavaScript library and instantiates the map through the `ngAfterViewInit` hook.

   <Callout icon="📘" theme="info">
     Note

     Replace `{YOUR_API_KEY}` with a valid HERE API key.
   </Callout>

4. Open the `jsmap.component.html` file, and then replace the file contents with the following code:
   ```html
   <div #map id="map"></div>
   ```

5. Open the `jsmap.component.css` file, and then add the following style:
   ```css
   #map {
     width: 100%;
     height: 500px;
   }
   ```

6. In the `jsapi-angular/src/app` directory, open the `app.component.html` file, and then replace the file content with following code:
   ```html
   <app-jsmap></app-jsmap>
   ```

7. In the same directory, open the `app.component.ts` file and add the following elements:

   * Add the `JsmapComponent` import statement:
     ```javascript
     import { JsmapComponent } from './jsmap/jsmap.component';
     ```

   * In the `imports` array, add `JsmapComponent`:
     ```javascript
     imports: [RouterOutlet, JsmapComponent],
     ```

   See the following updated `app.component.ts` file for reference:

   ```javascript
   import { Component } from '@angular/core';
   import { RouterOutlet } from '@angular/router';
   import { JsmapComponent } from './jsmap/jsmap.component';

   @Component({
     selector: 'app-root',
     standalone: true,
     imports: [RouterOutlet, JsmapComponent],
     templateUrl: './app.component.html',
     styleUrls: ['./app.component.css']
   })
   export class AppComponent {
     title = 'jsapi-angular';
   }
   ```

8. Verify that the map renders correctly by navigating to the `http://localhost:4200/` address in the browser.

**Result**: The browser renders a static map centered on Berlin, at zoom level `13`, in the viewport that is `500` pixels high and takes `100%` of the enclosing container's width, similar to the following example:
![Basic static map component rendered with the HERE Maps API for JavaScript](https://files.readme.io/e805e2d717a7945857daaef3728d2a7c8869011f5a50e4c70b6924bc72f9dafe-width100-31.png)

## Resize the map

A static map with a predetermined size cannot be changed during runtime.

You can improve a static map by adding dynamic resizing to make the map canvas react and adapt to the changes in the viewport size, for example, when the user expands the browser window.

To achieve that, the map needs an explicit `resize()` method call to adjust to the new dimensions of the container. This example uses `simple-element-resize-detector` to demonstrate how you can resize a map within an Angular component.

1. In Angular CLI, ensure that your working directory is the `jsapi-angular` directory.

2. Enter the following commands :
   ```shell
   npm install simple-element-resize-detector --save
   npm install @types/simple-element-resize-detector --save-dev
   ```

3. From the `src/app/jsmap` directory, open the `jsmap.component.ts` file, and then adjust the import statements by adding the `simple-element-resize-detector` library, as shown in the following example:
   ```javascript
   import { Component, ViewChild, ElementRef } from '@angular/core';
   import '@here/maps-api-for-javascript';
   import onResize from 'simple-element-resize-detector'; // New import statement
   ```

4. Update `ngAfterViewInit` method with the `map.getViewPort().resize()` method call, as shown in the following code snippet:
   ```javascript
     ngAfterViewInit(): void {
       if (!this.map && this.mapDiv) {
         const platform = new H.service.Platform({
           apikey: '{YOUR_API_KEY}'
         });
         const layers = platform.createDefaultLayers();
         const map = new H.Map(
           this.mapDiv.nativeElement,
           (layers as any).vector.normal.map,
           {
             pixelRatio: window.devicePixelRatio,
             center: {lat: 52.5, lng: 13.4},
             zoom: 13,
           },
         );
         onResize(this.mapDiv.nativeElement, () => {
           map.getViewPort().resize();
         }); // Sets up the event listener to handle resizing
         this.map = map;
       }
     }
   ```

**Result**: The component adjusts dynamically to the changes in the size of the enclosing browser window.

## Set the map to respond to input parameters

Use another component to take your input to change the zoom level and the center of the map.

1. Create a new component by entering the following command in Angular CLI:
   ```shell
   ng generate component mapposition
   ```

2. Navigate to the `src/app/mapposition` directory, and then open the `mapposition.component.html` file.

3. Replace the default content of the `mapposition.component.html` file with the following code:

   ```html
   <div class="input-group">
     <label for="zoom">Zoom:</label>
     <input
       id="zoom"
       (change)="notify.emit($event)"
       name="zoom"
       type="number"
       value="13"
     />
   </div>
   <div class="input-group">
     <label for="lat">Latitude:</label>
     <input
       id="lat"
       (change)="notify.emit($event)"
       name="lat"
       type="number"
       value="52.5"
     />
   </div>
   <div class="input-group">
     <label for="lng">Longitude:</label>
     <input
       id="lng"
       (change)="notify.emit($event)"
       name="lng"
       type="number"
       value="13.4"
     />
   </div>
   ```

   <Callout icon="📘" theme="info">
     Note

     The `mapposition` component has three input fields: `zoom`, `latitude` and `longitude`. The new code introduces a `change` event listener that redispatches events for each input field to the parent component.
   </Callout>

4. From the `src/app/mapposition/` directory, open the `mapposition.component.css` file, and then replace the default contents with the following basic style configuration:
   ```css
   .input-group {
     margin-bottom: 5px;
     margin-top: 5px;
     display: flex;
     align-items: center;
   }

   label {
     width: 100px;
     font-weight: bold;
   }

   input[type="number"] {
     width: 100px;
     padding: 5px;
     margin-left: 10px;
     border: 1px solid #ccc;
     border-radius: 4px;
   }

   input[type="number"]:focus {
     border-color: #007bff;
     outline: none;
   }
   ```

5. From the `src/app/mapposition/` directory, open the `mapposition.component.ts` file, and then replace the file content with the following code:

   ```javascript
   import { Component, Output, EventEmitter } from '@angular/core';

   @Component({
     selector: 'app-mapposition',
     standalone: true,
     templateUrl: './mapposition.component.html',
     styleUrls: ['./mapposition.component.css']
   })
   export class MappositionComponent {

     @Output() notify = new EventEmitter();

   }
   ```

   <Callout icon="📘" theme="info">
     Note

     This TypeScript part of the component uses the `@Output` decorator and the `EventEmitter` class to notify the parent component about the changes in the user input.
   </Callout>

6. From the `src/app` directory, open the `app.component.html` file, and then replace the file contents with the following code:

   ```html
   <app-jsmap
     [zoom]="zoom"
     [lat]="lat"
     [lng]="lng"
   ></app-jsmap>
   <app-mapposition
     (notify)="handleInputChange($event)"
   ></app-mapposition>
   ```

   <Callout icon="📘" theme="info">
     Note

     This code uses the parent `app` component to pass the values between the map and input fields.
   </Callout>

7. From the `src/app` directory, open the `app.component.ts` file, and then add a change handler by replacing the file content with the following code:

   ```javascript
   import { Component } from '@angular/core';
   import { RouterOutlet } from '@angular/router';
   import { JsmapComponent } from './jsmap/jsmap.component';
   import { MappositionComponent } from './mapposition/mapposition.component'; // Imports MappositionComponent

   @Component({
     selector: 'app-root',
     standalone: true,
     imports: [RouterOutlet, JsmapComponent, MappositionComponent], // Adds MappositionComponent to the AppComponent template
     templateUrl: './app.component.html',
     styleUrls: ['./app.component.css']
   })
   export class AppComponent {
     title = 'jsapi-angular';

     // Initialized by the constructor, these properties store the current zoom level and coordinates (latitude and longitude) for the map
     constructor() {
       this.zoom = 13;
       this.lat = 52.5;
       this.lng = 13.4;
     }

     zoom: number;
     lat: number;
     lng: number;

     // Updates the zoom, lat, and lng properties based on user input.
     handleInputChange(event: Event) {
       const target = <HTMLInputElement> event.target;
       if (target) {
         if (target.name === 'zoom') {
           this.zoom = parseFloat(target.value);
         }
         if (target.name === 'lat') {
           this.lat = parseFloat(target.value);
         }
         if (target.name === 'lng') {
           this.lng = parseFloat(target.value);
         }
       }
     }
   }
   ```

   **Result**: The change handler updates the values according to the user's input and Angular passes these values to the `jsmap` component.

8. From the `src/app/jsmap` directory, open the `jsmap.component.ts` file, and then perform the following actions:
   1. Adjust the first import statement to include `Input` and `SimpleChanges` classes, as shown in the following example:
      ```javascript
      import { Component, ViewChild, ElementRef, Input, SimpleChanges } from '@angular/core';
      ```
   2. Within the `JsmapComponent` class, after the existing `ngAfterViewInit` hook definition, add `@Input` decorators for zoom, latitude, and longitude, and then add the `ngOnChanges` hook definition, as shown in the following code snippet:
      ```javascript
      @Input() public zoom = 13;
      @Input() public lat = 52.5;
      @Input() public lng = 13.4;

      ngOnChanges(changes: SimpleChanges) {
        if (this.map) {
          if (changes['zoom'] !== undefined) {
            this.map.setZoom(changes['zoom'].currentValue);
          }
          if (changes['lat'] !== undefined) {
            this.map.setCenter({lat: changes['lat'].currentValue, lng: this.lng});
          }
          if (changes['lng'] !== undefined) {
            this.map.setCenter({lat: this.lat, lng: changes['lng'].currentValue});
          }
        }
      }
      ```

**Result**: Now, your Angular application can take your input with the help of the `mapposition` component, store the state in the `app` component, and then update the `jsmap` component so that the map responds to the input.

The following example demonstrates how the Angular application responds to the input by setting the coordinates to center the map on Berlin, and then increasing the zoom level:
![Map component that reacts to input](https://files.readme.io/583fb7864f26d90b8430514bd4372799dc88c790e8a0ca2627f8053b2dedaad2-map-component-user-input-31.png)

## Enable dragging and zooming

Further increase the interactivity of your map by enabling map manipulation in the form of dragging or zooming in or out of the view.

To achieve this behavior, add the `mapviewchange` listener to the `H.Map` instance, and then update the `app` state with the help of the `EventEmitter`.

1. In the `app.component.ts` file, update the `App` state by adding the following code:
   ```javascript
     handleMapChange(event: H.map.ChangeEvent) {
       if (event.newValue.lookAt) {
         const lookAt = event.newValue.lookAt;
         this.zoom = lookAt.zoom;
         this.lat = lookAt.position.lat;
         this.lng = lookAt.position.lng;
       }
     }
   ```

2. In the `app.component.html` file, replace the current content with the following code:
   ```html
   <app-jsmap
     [zoom]="zoom"
     [lat]="lat"
     [lng]="lng"
     (notify)="handleMapChange($event)"
   ></app-jsmap>
   <app-mapposition
     [zoom]="zoom"
     [lat]="lat"
     [lng]="lng"
     (notify)="handleInputChange($event)"
   ></app-mapposition>
   ```

3. Update the `jsmap.component.ts` file by performing the following actions:
   1. In the `jsmap.component.ts` file, adjust the import statement by adding the `Output` and `EventEmitter` classes, as shown in the following example:
      ```javascript
      import { Component, ViewChild, ElementRef, Input, SimpleChanges, Output, EventEmitter } from '@angular/core';
      ```

   2. Update the `ngAfterViewInit` hook by attaching the listener that enables the interactive behavior after the map instantiation:
      ```javascript
      map.addEventListener('mapviewchange', (ev: H.map.ChangeEvent) => {
        this.notify.emit(ev)
      });
      new H.mapevents.Behavior(new H.mapevents.MapEvents(map));
      ```

   3. Update the `ngOnChanges` method to throttle the unnecessary map updates:
      ```javascript
        private timeoutHandle: any;
        @Output() notify = new EventEmitter();

        ngOnChanges(changes: SimpleChanges) {
            clearTimeout(this.timeoutHandle);
            this.timeoutHandle = setTimeout(() => {
              if (this.map) {
                if (changes['zoom'] !== undefined) {
                  this.map.setZoom(changes['zoom'].currentValue);
                }
                if (changes['lat'] !== undefined) {
                  this.map.setCenter({lat: changes['lat'].currentValue, lng: this.lng});
                }
                if (changes['lng'] !== undefined) {
                  this.map.setCenter({lat: this.lat, lng: changes['lng'].currentValue});
                }
              }
            }, 100);
        }
      ```

4. In the `mapposition.component.ts` file, update the component to reflect the current position of the map:
   1. Import the `Input` decorator from the `@angular/core`, as shown in the following example:
      ```javascript
      import { Component, Output, EventEmitter, Input } from '@angular/core';
      ```
   2. Add the following input parameters in the class body:
      ```javascript
        @Input() public zoom = 13;
        @Input() public lat = 52.5;
        @Input() public lng = 13.4;
      ```

5. In the `mapposition.component.html` file, adjust the template by replacing the file content with the following code:
   ```html
   <div class="input-group">
     <label for="zoom">Zoom:</label>
     <input
       id="zoom"
       (change)="notify.emit($event)"
       name="zoom"
       type="number"
       [value]="zoom"
     />
   </div>
   <div class="input-group">
     <label for="lat">Latitude:</label>
     <input
       id="lat"
       (change)="notify.emit($event)"
       name="lat"
       type="number"
       [value]="lat"
     />
   </div>
   <div class="input-group">
     <label for="lng">Longitude:</label>
     <input
       id="lng"
       (change)="notify.emit($event)"
       name="lng"
       type="number"
       [value]="lng"
     />
   </div>
   ```

**Result**: The resulting application consist of the interactive map and input fields. When you interact with the map, the application automatically updates the input fields, as shown in the following example:
![Interactive Map component](https://files.readme.io/a5943c52c45f095316e3b1c90157ac0ef46b36128d5012750ea2908fa75f4692-interactive-map-31.png)

## Optional: Add markers

The Angular application that you just created might serve as a template for adding further customizations or extensions that suit your business objectives. For example, you can add map markers to provide a quick and efficient way to visually represent the location of a point of interest on a map.

1. In the `jsmap.component.ts` file, set the modify the `map` property to center on the area where you want to place the markers, as shown in the following example:
   ```javascript
   const map = new H.Map(
     this.mapDiv.nativeElement,
     (layers as any).vector.normal.map,
     {
       pixelRatio: window.devicePixelRatio,
       // In this example, the map centers on
       // the HERE Technologies office in Berlin:
       zoom: 19,
       center: { lat: 52.53074, lng: 13.38492 }
     },
   );
   ```

2. Create a variable storing the marker SVG markup:
   ```javascript
   const mapMarkerSvg = `<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 48 48" width="48" height="48" fill="none" stroke="#0F1621" stroke-width="4" stroke-linecap="round" stroke-linejoin="round">
     <path fill="#00AFAA" d="M24 4C16.26 4 10 10.26 10 18c0 9.74 14 26 14 26s14-16.26 14-26c0-7.74-6.26-14-14-14z"/>
     <circle cx="24" cy="18" r="6" fill="#1D1E1F"/>
   </svg>`
   ```

3. Set up a marker with an SVG icon at a specific location on the map by defining the following variables:
   ```javascript
   const icon = new H.map.Icon(mapMarkerSvg);
   const coords = {lat: 52.53074, lng: 13.38492};
   const marker = new H.map.Marker(coords, { data: null, icon: icon });
   ```

4. Add the marker to the map, making it visible at the specified coordinates:
   ```javascript
   map.addObject(marker);
   ```

5. Center the map view on the location of the marker:
   ```javascript
   map.setCenter(coords);
   ```

**Result**: The map in your Angular application now centers on and displays a marker at the selected location, as illustrated in the following figure:

![Map component that displays markers](https://files.readme.io/f981f775e4c3524bc121bb1b861dbc31e67d2db52b64cf4bd38d339d2e22d746-default-markers-31.png)

For more information on markers, see [Marker Objects](doc:marker-objects-31).

## Code samples

The following sections contains the full code samples for `Jsmap`, `App`, and `Mapposition`, which are the main Angular components used in this tutorial.

### Jsmap component

View the `jsmap.component.ts` source code.

<Accordion title="Click to expand/collapse the code sample">
  ```javascript
  import { Component, ViewChild, ElementRef, Input, SimpleChanges, Output, EventEmitter } from '@angular/core';
  import '@here/maps-api-for-javascript';
  import onResize from 'simple-element-resize-detector';

  @Component({
    selector: 'app-jsmap',
    standalone: true,
    templateUrl: './jsmap.component.html',
    styleUrls: ['./jsmap.component.css']
  })
  export class JsmapComponent {

    private map?: H.Map;

    @ViewChild('map') mapDiv?: ElementRef;

      ngAfterViewInit(): void {
      if (!this.map && this.mapDiv) {
        const platform = new H.service.Platform({
          apikey: 'YOUR_HERE_API_KEY'
        });
        const layers = platform.createDefaultLayers();
        const map = new H.Map(
          this.mapDiv.nativeElement,
          (layers as any).vector.normal.map,
          {
            pixelRatio: window.devicePixelRatio,
            center: {lat: 52.53074, lng: 13.38492},
            zoom: 19,
          },
        );
        onResize(this.mapDiv.nativeElement, () => {
          map.getViewPort().resize();
        });
        this.map = map;

        map.addEventListener('mapviewchange', (ev: H.map.ChangeEvent) => {
          this.notify.emit(ev)
        });
        new H.mapevents.Behavior(new H.mapevents.MapEvents(map));

        const mapMarkerSvg = `<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 48 48" width="48" height="48" fill="none" stroke="#0F1621" stroke-width="4" stroke-linecap="round" stroke-linejoin="round">
          <path fill="#00AFAA" d="M24 4C16.26 4 10 10.26 10 18c0 9.74 14 26 14 26s14-16.26 14-26c0-7.74-6.26-14-14-14z"/>
          <circle cx="24" cy="18" r="6" fill="#1D1E1F"/>
        </svg>`

        const icon = new H.map.Icon(mapMarkerSvg);
        const coords = {lat: 52.53074, lng: 13.38492};
        const marker = new H.map.Marker(coords, { data: null, icon: icon });

        map.addObject(marker);
        map.setCenter(coords);
      }
    }

    @Input() public zoom = 13;
    @Input() public lat = 52.5;
    @Input() public lng = 13.4;

    private timeoutHandle: any;
    @Output() notify = new EventEmitter();

    ngOnChanges(changes: SimpleChanges) {
        clearTimeout(this.timeoutHandle);
        this.timeoutHandle = setTimeout(() => {
          if (this.map) {
            if (changes['zoom'] !== undefined) {
              this.map.setZoom(changes['zoom'].currentValue);
            }
            if (changes['lat'] !== undefined) {
              this.map.setCenter({lat: changes['lat'].currentValue, lng: this.lng});
            }
            if (changes['lng'] !== undefined) {
              this.map.setCenter({lat: this.lat, lng: changes['lng'].currentValue});
            }
          }
        }, 100);
    }
  }
  ```
</Accordion>

<Callout icon="📘" theme="info">
  Note

  Replace `YOUR_HERE_API_KEY` in the previous code sample with a valid API key.
</Callout>

### App component

View the `app.component.ts` source code.

<Accordion title="Click to expand/collapse the code sample">
  ```javascript
  import { Component } from '@angular/core';
  import { RouterOutlet } from '@angular/router';
  import { JsmapComponent } from './jsmap/jsmap.component';
  import { MappositionComponent } from './mapposition/mapposition.component';

  @Component({
    selector: 'app-root',
    standalone: true,
    imports: [RouterOutlet, JsmapComponent, MappositionComponent],
    templateUrl: './app.component.html',
    styleUrls: ['./app.component.css']
  })
  export class AppComponent {
    title = 'jsapi-angular';

    constructor() {
      this.zoom = 13;
      this.lat = 52.5;
      this.lng = 13.4;
    }

    zoom: number;
    lat: number;
    lng: number;

    handleInputChange(event: Event) {
      const target = <HTMLInputElement> event.target;
      if (target) {
        if (target.name === 'zoom') {
          this.zoom = parseFloat(target.value);
        }
        if (target.name === 'lat') {
          this.lat = parseFloat(target.value);
        }
        if (target.name === 'lng') {
          this.lng = parseFloat(target.value);
        }
      }
    }

    handleMapChange(event: H.map.ChangeEvent) {
      if (event.newValue.lookAt) {
        const lookAt = event.newValue.lookAt;
        this.zoom = lookAt.zoom;
        this.lat = lookAt.position.lat;
        this.lng = lookAt.position.lng;
      }
    }
  }
  ```
</Accordion>

### Mapposition component

View the `mapposition.component.ts` source code.

<Accordion title="Click to expand/collapse the code sample">
  ```javascript
  import { Component, Output, EventEmitter, Input } from '@angular/core';

  @Component({
    selector: 'app-mapposition',
    standalone: true,
    templateUrl: './mapposition.component.html',
    styleUrls: ['./mapposition.component.css']
  })
  export class MappositionComponent {

    @Output() notify = new EventEmitter();

    @Input() public zoom = 13;
    @Input() public lat = 52.5;
    @Input() public lng = 13.4;

  }
  ```
</Accordion>

## Optional: Switch to the HARP engine

You can configure your map to provide users with up-to-date, customizable, and visually engaging map experiences by configuring your map to use the [HARP engine](https://www.here.com/docs/bundle/maps-api-for-javascript-migration-guide/page/README.html).

1. In the `tsconfig.json` file, within the `compilerOptions` object, add the following option:
   ```javascript
   "allowJs": true
   ```

2. In the `main.ts` file, add the following statement:
   ```javascript
   import '@here/maps-api-for-javascript/bin/mapsjs.bundle.harp'
   ```

3. In the `jsmap.component.ts` file, edit the `layers` and `map` variables to use the HARP engine for map instatiation, as shown in the following example:
   ```javascript
   // Declare HARP as the engine type within
   // the layers variable
   const layers = platform.createDefaultLayers({ engineType: H.Map.EngineType.HARP });
   const map = new H.Map(
     this.mapDiv.nativeElement,
     (layers as any).vector.normal.map,
     {
       // Set the engine type for the H.Map instance
       engineType: H.Map.EngineType.HARP,
       pixelRatio: window.devicePixelRatio,
       zoom: 19,
       center: { lat: 52.53074, lng: 13.38492 }
     },
   );
   ```

The swich to the HARP engine is reflected by a change in the map's look and feel, as shown in the following example:

![An Angular app that with HERE maps using the HARP engine](https://files.readme.io/6cda68db846121d3fe177ce9bd156f98414425b0879947816ff6e69e680dd941-harp-engine-31.png)

## Next steps

To further explore the design and features of the Maps API for JavaScript, see the [API Reference](https://www.here.com/docs/bundle/maps-api-for-javascript-api-reference/page/index.html).
