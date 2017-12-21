#### Specifies how and where DrawerJs will store its canvas data. 

***
### Configuration for Saving Data
```
contentConfig: {
    saveAfterInactiveSec: 5,
    saveInHtml: false,
    imagesContainer: '#drawer-canvas-images-container',
    canvasDataContainer: '#drawer-canvas-data-container'
}
```
### Saving Data in HTML or a Container
* `saveInHtml`:
    * Specifies whether DrawerJs' canvas element will save its content to the underlying image element.
    * If `true`, the canvas objects will be serialized into JSON and stored within the `data-canvas-serialized` attribute of the image container.
    * Note that the resulting JSON could be huge for canvases with a lot of objects or freehand drawings.
* `saveAfterInactiveSec`:
    * Specifies the number of seconds to wait after the last user interaction before saving the drawing.
* `imagesContainer`:
    * Specifies an external container element to hold the canvas images' data.
    * The contents of the canvas will be serialized into a base64-encoded PNG and stored as JSON-encoded text within the specified container.
    * This technique can be used for storing rendered images separately from the content.
* `canvasDataContainer`:
    * Specifies an external container element to hold the canvas data.
    * The contents of the canvas will be serialized into JSON objects containing all the canvas' vector objects and their parameters like angles, colors etc.
    * This technique can be used for storing canvas vector data separately from the content.
### Saving Data Using a Custom Function
```


var drawerPlugins = [
    // Drawing tools
    'Pencil',
    'Eraser',
    'Text',
    'Line',
    'ArrowOneSide',
    'ArrowTwoSide',
    'Triangle',
    'Rectangle',
    'Circle',
    'Polygon',
    // Drawing options
    'Color',
    'ShapeBorder',
    'BrushSize',
    'Resize',
    'ShapeContextMenu'
];
var saveContent = function() {
    var html = $('#canvas-editor').html();
    localStorage.setItem('html', html);
    localStorage.setItem('canvas_id', canvas.id);
};
var loadContent = function() {
    var html = localStorage.getItem('html');
    var canvasId = localStorage.getItem('canvas_id');
    if(html && canvasId) {
        $('#canvas-editor').html(html);
        canvas.id = canvasId;
        return true;
    }
    return false;
};
var canvas = null;
$(document).ready(function () {
    canvas = new DrawerJs.Drawer(null, {
        plugins: drawerPlugins,
        contentConfig: {
            saveInHtml: false,
            saveCanvasData: function(canvasId, canvasData) {
                localStorage.setItem('canvas_' + canvasId, JSON.stringify(canvasData));
                saveContent();
            },
            loadCanvasData: function(canvasId) {
                return localStorage.getItem('canvas_' + canvasId);
            },
            saveImageData: function(canvasId, imageData) {
                localStorage.setItem('image_' + canvasId, JSON.stringify(imageData));
            },
            loadImageData: function(canvasId) {
                return localStorage.getItem('image_' + canvasId);
            }
        }
    }, 600, 600);
    if(!loadContent()){
        $('#canvas-editor').append(canvas.getHtml());
    }
    canvas.onInsert();
});
```
* `saveInHtml`:
    * Specifies whether DrawerJs' canvas element will save its content to the underlying image element.
    * If `true`, the canvas objects will be serialized into JSON and stored within the `data-canvas-serialized` attribute of the image container.
    * Note that the resulting JSON could be huge for canvases with a lot of objects or freehand drawings.
* `saveCanvasData`:
    * Specifies a function that will be called when an editable DrawerJs element needs to store its canvas data.
* `loadCanvasData`: 
    * Specifies a function that will be called when an editable DrawerJs element needs to load its canvas data.
* `saveImageData`:
    * Specifies a function that will be called when an editable DrawerJs element needs to load base64/png image data.
* `loadImageData`:
    * Specifies a function that will be called when an editable DrawerJs element needs to save base64/png image data.