# Tile viewer for OSRM

OSRM, as of version 5.0, supports serving of Mapbox Vector Tiles to view the
routing graph that's stored in memory.

Tiles can be retrieved from `osrm-routed` at URLs like this:

  http://127.0.0.1:5000/tile/v1/car/tile(1321,3177,13).mvt

This tool is a simple HTML viewer that uses [Mapbox GL JS](https://www.mapbox.com/mapbox-gl-js/)
to make a slippy map to view the tiles in a browser.

Note of warning: as you zoom out, the tiles get bigger and bigger (each tile contains more data).  Beyond
about zoom 12, tiles are >1MB in size, and will be very slow to display in your browser.  Avoid zooming out
too far.  If you zoom out to Zoom 0, you'll get tiles that are multiple GB in size for a whole planet datafile,
and, well, your whole computer will likely freeze up.

You'll probably need to edit `index.html` and set the URL for `osrm-routed`, and the initial coordinates/zoom level.
