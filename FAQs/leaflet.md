# Leaflet FAQs

## resizing markers based on zoom
* Q: How can make I sure circle markers (or other custom marker icons) resize correctly when zooming?
* A: Because of the way [Leaflet zoom levels](https://leafletjs.com/examples/zoom-levels/) work, (essentially the width and height of the map is 256·2<sup>zoomlevel</sup> pixels) you need to calculate the zoom ratio like this: 2<sup>(newZoom - oldZoom)</sup>. So you can calculate the new size of the marker like this:
newSize = oldSize * 2<sup>(newZoom - oldZoom)</sup>
* Example: Let's say your inital zoom level is 10. The size of the world in the map is 256 * 2<sup>10</sup> = 262.144 pixels. You zoom in and go from zoom level 10 to 11. The new size of the world will be 256 * 2<sup>11</sup> = 524.288 pixels. Since the world has doubled in size, it's appropriate to increase the size of the marker to twice it's previous size as well. (With the formula from above: 2<sup>(11-10)</sup> = 2<sup>1</sup>) Same thing if you go back to zoom level 10, now the size needs to be half, which would be 2<sup>-1</sup> 
