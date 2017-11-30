#### Use the Public API to control DrawerJs or control any selected object on DrawerJs' canvas. 

***
### Entering Edit Mode of DrawerJs
```
drawer.api.startEditing();
```
* This method activates the DrawerJs instance. 
* This method is equivalent to clicking into the canvas element to activate DrawerJs. 

### Exit Edit Mode of DrawerJs
```
drawer.api.stopEditing();
```
* This method deactivates the DrawerJs instance. 
* This method is equivalent to clicking outside the canvas element to deactivate DrawerJs. 

### Load Canvas Data into DrawerJs
```
drawer.api.loadCanvasFromData(serializedCanvasData);
```
* This method loads serialized canvas data into DrawerJs. 
* The data is given as an parameter. 

### Save Canvas Data To Storage
```
drawer.api.saveCanvas();
```
* This method syncs DrawerJs' canvas data with storage which are defined in DrawerJs' options settings. 
* In fact this call will fire custom code when defined here: 
    * `saveCanvasData`

### Get Canvas Data
```
var serializedCanvasData = drawer.api.getCanvasAsJSON();
```
* This method gets serialized canvas data. 
* Returns data as a json string. 

### Save Image To Storge
```
drawer.api.saveCanvasImage();
```
* This method saves current canvas as an image to storage which is defined in DrawerJs' options settings. 
* In fact this call will fire custom code when defined here: 
    * `saveImageData`

### Get Image from Canvas Data
```
var imageData = drawer.api.getCanvasAsImage();
```
* This method returns a string with image data encoded in base64/png. 

### Insert Image
```
var imgEl = 'img src="http://yourdomain.com/assets/image.jpg"';
                         
var options = {};
options.scaleDownLargeImage = true;
options.centerImage = true;
      
if (!options.scaleDownLargeImage) {
    options.left = left;
    options.top = top;
    options.scaleX = scaleX;
    options.scaleY = scaleY;
};
drawer.api.addImage(imgEl, options);
```
* This method inserts an image to canvas.
* The image source can be an any `img` [HTML element](https://developer.mozilla.org/de/docs/Web/API/HTMLImageElement).
* Alternatively the image source can be a [JavaScript image class](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/Image). 
* Parameters:
    * `imgEl`
        * Type: string 
        * A `img` HTML element or a JavaScript `image` class. 
    * `options`
        * Type: object 
        * An object with these configuration parameters: 
            * `scaleDownLargeImage`
                * Type: boolean 
                * If set to true the inserted image is automatically scaled down to fit into canvas. 
                * If this parameter is set any `scaleX` and `scaleY` parameters will be ignored. 
                * The default value is `true`. 
            * `centerImage`
                * Type: boolean 
                * If set to true the inserted image will be centered on the canvas. 
                * If this parameter is set any `left` and `top` parameters will be ignored. 
                * The default value is `true`. 
            * `left`
                * Type: integer 
                * The inserted image will be positioned at given left position in px. 
                * The `left` and `top` parameters may not be used in conjunction with parameter `centerImage`. 
                * The default value is `0`. 
            * `top`
                * Type: integer 
                * The inserted image will be positioned at given top position in px. 
                * The `left` and `top` parameters may not be used in conjunction with parameter `centerImage`. 
                * The default value is `0`. 
            * `scaleX`
                * Type: integer 
                * The inserted image will be scaled on x coordinate. 
                * The `scaleX` and `scaleY` parameters may not be used in conjunction with parameter `scaleDownLargeImage`. 
                * The default value is `0`. 
            * `scaleY`
                * Type: integer
                * The inserted image will be scaled on y coordinate. 
                * The `scaleX` and `scaleY` parameters may not be used in conjunction with parameter `scaleDownLargeImage`. 
                * The default value is `0`. 

### Insert Image (from URL)
```
var imgSrc = 'http://yoursite/images/example1.jpg'
var options = {};
drawer.api.addImageFromUrl(imgSrc, options);
```
* This method inserts an image to DrawerJs' canvas. 
* The image source can be any URL. 
* Parameters:
    * `imgSrc`
        * Type: string 
        * A URL to any allowed image type. 
    * `options`
        * Type: object 
        * Please refer to [Insert Image](#insert-image) for a detailed explanation for options object. 

### Add Image as Background
```
var imgEl = 'img src="http://yourdomain.com/assets/image.jpg"';
var options = {};
drawer.api.setBackgroundImage(imgEl, options);
```
* This method adds an image as background to DrawerJs' canvas. 
* The image source can be an any `img` [HTML element](https://developer.mozilla.org/de/docs/Web/API/HTMLImageElement).
* Alternatively the image source can be a [JavaScript image class](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/Image).  
* Parameters:
    * `imgEl`
        * Type: string 
        * A `img` HTML element or a JavaScript `image` class. 
    * For the `options` please refer to documentation [Image as background](https://github.com/carstenschaefer/DrawerJs/wiki/image-as-background). 

### Add Image as Background (from URL)
```
var imgSrc = 'http://yoursite/images/example1.jpg'
var options = {};
drawer.api.setBackgroundImageFromUrl(imgSrc, options);
```
* This method adds an image as background to DrawerJs' canvas. 
* The image source can be any URL. 
* Parameters:
    * `imgSrc`
        * Type: string 
        * A URL to any allowed image type. 
    * `options`
        * Type: object 
        * For the `options` please refer to documentation [Image as background](https://github.com/carstenschaefer/DrawerJs/wiki/image-as-background). 

### Resize Canvas Element
```
var width = 500;
var height = 300;
drawer.api.setSize(width, height);
```
* This method will resize the DrawerJs canvas element. 
* This method is equivalent to resizing the canvas element using the resize anchor in bottom right corner of canvas element when `Resize`: plugin is loaded. 
* Parameters:
    * `width`:
        * Type: Number 
        * Width in px 
    * `height`:
        * Type: Number 
        * Height in px 

### Reload Config
```
var drawerPlugins = [
    'Pencil',
    'Eraser',
    'Text',
    'ShapeContextMenu'
];
var options = {plugins: drawerPlugins};
drawer.api.updateOptions(options);
```
* This method will reload the DrawerJs' config. 
* This method is equivalent to restart DrawerJs after the configuration has altered. 
* Parameter:
    * `options`:
        * DrawerJs' configuration object. 

### Load or Unload Specific Plugin
```
drawer.api.unloadPlugin('Text');
drawer.api.loadPlugin('Eraser');
```
* These methods will load or unload a specific plugin. 
* Parameter:
    * `plugin`:
        * Type: string 
        * Name of plugin to load or unload. 

### Positioning of Context Menu
```
var left = 300;
var top  = 510;
var fitInViewPort = true;
drawer.api.contextMenuSetPosition(left, top, fitInViewPort);
```
* This method repositioning the context menu after it was triggered. 
* Parameter:
    * `left`:
        * Type: integer 
        * Defines left positioning of context menu in px. 
    * `top`:
        * Type: integer 
        * Defines top positioning of context menu in px. 
    * `fitInViewPort`:
        * Type: boolean 
        * If set to `true` the context menu will always be shown within viewport in case `left` or `top` parameters will show context menu outside of viewport. 
        * If set to `false` the context menu may eventually be shown without viewport. 

### Setting Image of Inactive DrawerJs
Set image as an object
```
url = 'http://kingofwallpapers.com/picture/picture-015.jpg'; 
image = new Image();
image.onload = function(){
    drawer.api.setInactiveDrawerImage(image);
};
image.src = url;
```

Set image as url
```
url = 'http://kingofwallpapers.com/picture/picture-015.jpg'; 
drawer.api.setInactiveDrawerImage(url);
```
* This method will set an image that is shown when DrawerJs is inactive. 

### Minimizing and Restoring
```
drawer.api.minimizeCanvas();
drawer.api.restoreCanvas();
```
* This methods minimizes and restores a DrawerJs instance. 
* This method is equivalent to clicking the `MinimizeButton` or `RestoreButton`. 

### Enter and Exit Fullscreen Mode
```
drawer.api.fullscreenOn();
drawer.api.fullscreenOff();
```
* This methods starts and ends the fullscreen mode of the DrawerJs instance.
* This method is equivalent to clicking the `FullscreenButton`. 

### Zooming
```
var zoomValue = 1.2;
zoomCenterX = 180,
zoomCenterY = 310;
drawer.api.setZoom(zoomValue, zoomCenterX, zoomCenterY);
drawer.api.restoreDefaultZoom();
```
* This method `setZoom()` zooms the canvas to the given level found in `zoomValue`. 
* Optionally the coordinates of canvas' new center point can be set. 
* Parameter of `setZoom()`: 
    * `zoomValue`:
        * Type: number 
        * Defines the zoom level. E.g. 1.2 = 120%. 
    * `zoomCenterX`:
        * Type: number. Optional. 
        * Defines the x coordinate of canvas' new center point. 
        * Allowed range: From 0 to current canvas width. 
    * `zoomCenter`:
        * Type: number. Optional. 
        * Defines the y coordinate of canvas' new center point. 
        * Allowed range: From 0 to current canvas width. 
* The method `restoreDefaultZoom()` will set zoom level to default value and resets position of center points. 


### Control Selected Objects
With this subsection of DrawerJs' API you will control specific selected objects on DrawerJs' canvas.  

Get Selected Object
```
var selectedObject = drawer.api.getSelectedObject();
```
* This method gets selected object.
* Needed for any further operations on it.

Bring Object Forwards
```
drawer.api.bringObjectForward(selectedObject);
```
* This method moves the selected object one step to front.
* Parameter: 
    * `selectedObject` get by `drawer.api.getSelectedObject()`

Bring Object to the Front
```
drawer.api.bringObjectToFront(selectedObject);
```
* This method moves the selected object to the front.
* Parameter:
    * `selectedObject` get by `drawer.api.getSelectedObject()`

Send Object Backwards
```
drawer.api.sendObjectBackwards(selectedObject);
```
* This method sends the selected object one step to back.
* Parameter:
    * `selectedObject` get by `drawer.api.getSelectedObject()`

Send Object to the Back
```
drawer.api.sendObjectToBack(selectedObject);
```
* This method sends the selected object to the back.
* Parameter:
    * `selectedObject` get by `drawer.api.getSelectedObject()`

Remove Object
```
drawer.api.removeObject(selectedObject);
```
* This method removes the selected from the canvas.
* Parameter:
    * `selectedObject` get by `drawer.api.getSelectedObject()`

Duplicate Object
```
drawer.api.duplicateObject(selectedObject);
```
* This method duplicates the selected object and inserts a copy of it into the canvas.
* Parameter:
    * `selectedObject` get by `drawer.api.getSelectedObject()`

### Set Active Color
```
drawer.api.setActiveColor(#hexColorCode);
```
* This method sets the active color for drawing or creating shapes. 
* This method is equivalent to select a color from DrawerJs' color palette.

### Get Drawer's Canvas Size
```
drawer.api.getSize();
```
* This method returns the following object showing all available options for its size. 
* Returned Object:
    * {Number} width: width of DrawerJs 
    * {Number} height: height of DrawerJs 
    * {Number} scrollTop: "Top" position including scrollTop value of parent elements 
    * {Number} scrollLeft: "Left" position including scrollLeft value of parent elements 
    * {Number} top: Absolute value of "top" position 
    * {Number} left: Absolute value of "left" position 

### Adding Text to Canvas
```
styles = {
    fontSize: 150,
    fill: "#00acec",
    opacity: 0.4
};
drawer.api.createText(100, 50, 'some text', styles);
```
* This method adds some text to the canvas. 
* Parameters:
    * positionX: left offset of new text object
    * positionY: top offset of new text object
    * text: text of new object
    * styles: object with CSS Styles