---
title: Maps CLI
author: Andrew Erdman
hidden: false
published_at: '2026-04-27T15:49:58.374Z'
---
<div class="cl-meta">[version: 2026.03] [domain: Maps CLI] [change: ADDED]</div>

Added support for additional file formats in the `--file` parameter of the `maps input put` command.

Previously, it only supported `FeatureCollection` objects provided via `GeoJSON` files.

Now, it supports:

* [GeoJson](https://geojson.org/) – Files containing either Feature or FeatureCollection objects.
* [Json Line](https://jsonlines.org/) – Files containing multiple Feature objects, each separated by a new line.