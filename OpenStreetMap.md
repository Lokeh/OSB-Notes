# On-device mobile vector rendering of OpenStreetMap

## Intro

Mapbox GL:
	- on-device vector rendering
	- the GL... it means GPU accelerated

Most common way of drawing a map was using raster tiles (basically an image)
As you zoom in, you're basically just scaling the image
So once you zoom in enough, you split from 1 tile to 4, to 16, etc. to accomodate resolution. Creates drastic changes in resolution/skippy
Rotating is also a problem, does not rotate well less than 90 deg.

Vector tiles:
	- they are just data (you don't "see" them)
	- Tile pyramid works pretty much the same, but the change in resolution is continuous ("non-integer levels of zoom")
		- zoom-dependent styling
			- line-width depend on zoom level
			- label-collision and details appear continuously

Vector/Raster combos:
	- All satellite imagery is raster
	- Combining raster base, vector features and labels
	- Style transitions: Smooth transition between day/night mode, etc.
	- Super-imposed videos to show live sections on a map

## Technical

### Mapbox GL Stack

Dual stack: native devices + JS. JS is not designed for mobile, uses heavy WebGL and is resource constrained

Working on node.js bindings, native stuff is in C++.

Native bindings for iOS/Android.

Uses slippy map URLs. Built on open standards

#### Vector tiles

Eliminate the database esp. for global maps
Instead of indexing DBs, we pre-tile
Pre-optimize ("polygon simplification")
Tile format spec is open on [GitHub](http://github.com/mapbox)
Works with OSM but can work with any tile data
Binary format

Tools:
	Create
		- mapnik.org
		- github.com/mapbox/tilelive-bridge
	Parsing
		- githubc.om/mapbox/mapbox-vector-tile.[js|py]

Style spec is also on github (JSON format) **WA: tooling for this??**

### Mobile potential

Mobile doesn't just mean phone: means *personal* & *hyper-local*
Contain ever-increasing number of sensors
e.g. ambient light: lower constrast map in dark room/night, brighter high contrast map when in bright room/daytime

Highlighting data on the map due to user specific criteria **WA: handicap accessible? is the business open? yelp reviews? games like ingress?*


## Q&A Interesting bits

- 2-1/2D just pushed to the JS side
- You can pull in GeoJSON at runtime
- You can pull in your own pre-processed data as well


