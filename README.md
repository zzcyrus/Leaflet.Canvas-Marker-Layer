# Leaflet.Canvas-Marker-Layer
A custom canvas marker layer, based on [Leaflet.Canvas-Markers](https://github.com/eJuke/Leaflet.Canvas-Markers), add **`userDrawFunc`** option to support custom canvas marker style.

# Demo

[Icons-Markers](https://zzcyrus.github.io/Leaflet.Canvas-Marker-Layer/examples/icons.html)

[Custom-canvas-circle-Markers](https://zzcyrus.github.io/Leaflet.Canvas-Marker-Layer/examples/circle.html)

[Custom-canvas-text-Markers](https://zzcyrus.github.io/Leaflet.Canvas-Marker-Layer/examples/text.html)


# Basic usage and api

Mostly same as [Leaflet.Canvas-Markers](https://github.com/eJuke/Leaflet.Canvas-Markers)


Attach `Leaflet.Canvas-Marker-Layer.js` from the `dist` folder  to your project.

```html
<script src="Leaflet.Canvas-Marker-Layer.js"></script>
```

Now you can init the layer with option **`userDrawFunc`**

```js
/**
 * @param layer         the layer object
 * @param marker        current marker object
 * @param pointPos      current marker's pixel position
 * @param size          current marker's icon size
 */

var layer = L.canvasMarkerLayer({
  userDrawFunc: function(layer, marker, pointPos, size){
    var ctx = layer._context;
    ctx.beginPath();
    ctx.arc(pointPos.x, pointPos.y, size[0] / 2, 0, 2 * Math.PI);
    ctx.fillStyle = 'rgba(255,12,0,0.4)';
    ctx.fill();
    ctx.closePath();
  }
}).addTo(map);

```

# Dev

```
git clone 
yarn
npm start
```