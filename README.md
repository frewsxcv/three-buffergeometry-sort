# three-buffergeometry-sort

I primarily made this so working with THREE.js BufferGeometry would be easier to work with. Some of this code is based on [this StackOverflow post](http://stackoverflow.com/a/18901830).

## How to use

```js
// Import this library
var BGSorter = require("three-buffergeometry-sort");

// Create your BufferGeometry with 'positions' attribute
this.points = new THREE.BufferGeometry();
this.points.addAttribute('position', positions);

// Initialize the sorter
var sorter = BGSorter();

function render() {
  // Sort positions in ascending order in terms of distance from camera every frame
  sorter.sort(this.points.attributes, cameraPosition);

  window.requestAnimationFrame(render);
}
window.requestAnimationFrame(render);
```

You can also make it sort every N frames

```js
var sorter = BGSorter(5);

function render() {
  // Sort positions every 5 frames
  sorter.sort(this.points.attributes, cameraPosition);

  window.requestAnimationFrame(render);
}
window.requestAnimationFrame(render);
```

## License

[Mozilla Public License version 2](https://www.mozilla.org/MPL/2.0/)
