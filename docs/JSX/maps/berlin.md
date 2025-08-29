---
title: Berlin
deprecated: false
hidden: false
icon: fad fa-file-lines
metadata:
  robots: index
---
<BerlinOverlay header="Berlin Historical Overlay (1789)" apiKey="rVczblKDUJs-XSyUkLooaPkP4wcqHPaOB3oFvO1on3M" />

<HTMLBlock>{`
  <body>
    <div class="page-header">
        <h1>Adding an Overlay to the Map</h1>
        <p>Display custom map tiles as an overlay</p>
    </div>
    <p>This example displays a movable map initially centered on the historical centre of <b>Berlin</b> (<i>52.515, °N, 13.405°E</i>) with an overlay of a historical map from 1789 on top of the base map. A public domain image was used as a source, and split it into individual map tiles. Additional tiles are only downloaded when the zoom level or location changes.</p>
    <div id="map"></div>
    <hr/>
    <h2>Credits</h2>
    <p>
      <span>Wikimedia Commons Images</span><br/>
        The tile source is based on <a href="https://commons.wikimedia.org/wiki/File%3AMap_de_berlin_1789_%28georeferenced%29.jpg" target="_blank">an image of Berlin in 1789</a> from Wikimedia.<br/>
        Images provided by Wikimedia Commons are under the copyright of their owners.<br/>
        However, almost all <a href="https://commons.wikimedia.org/wiki/Commons:Reusing_content_outside_Wikimedia" target="_blank">content hosted on Wikimedia Commons</a> may be freely reused subject to certain restrictions.<br/>
    </p>
    <h3>Code</h3>
    <p>
        The example uses the <a target="_blank" rel="nofollow" href="https://www.here.com/docs/bundle/maps-api-for-javascript-api-reference/page/H.map.provider.ImageTileProvider.html"><code>H.map.provider.ImageTileProvider</code></a> class for fetching our custom tiles. The <code>getUrl()</code> method constructs the URL of the tile for the specified column/row/zoom position. The result is displayed on the map as an additional layer using an instance of the <a target="_blank" rel="nofollow" href="https://www.here.com/docs/bundle/maps-api-for-javascript-api-reference/page/H.map.layer.TileLayer.html"><code>H.map.layer.TileLayer</code></a> class which has been created by passing in the image tile provider object.
    </p>

  </body>
`}</HTMLBlock>

<br />
