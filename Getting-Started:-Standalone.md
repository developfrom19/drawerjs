#### A simple example of using DrawerJs as a standalone component on a website.

***

### Adding to Site

```
<!DOCTYPE HTML>
<html>
    <head>
        <link rel="stylesheet" href="fonts/font-awesome/font-awesome.min.css" />
        <link rel="stylesheet" href="drawerJs/drawerJs.min.css" />
        <style>
            #canvas-editor {
                margin-top: 50px;
                margin-left: 50px;
            }
        </style>
    </head>
    <body>
        <div id="canvas-editor"></div>
        <script src="jQuery/jquery-1.10.1.min.js"></script>
        <script src="drawerJs/drawerJs.standalone.min.js"></script>
        <script src="drawerJs/drawerLocalization.js"></script>
        <script src="drawerJsConfig.js"></script>
        <script>
            $(document).ready(function () {
                var drawer = new DrawerJs.Drawer(null, {
                    texts: customLocalization,
                    plugins: drawerPlugins,
                    defaultImageUrl: '/images/drawer.jpg',
                    defaultActivePlugin : { name : 'Pencil', mode : 'lastUsed'},
                }, 600, 600);
                $('#canvas-editor').append(drawer.getHtml());
                drawer.onInsert();
            });
        </script>
    </body>
</html>
```
```
root
|
+--fonts
|  |
|  +--font-awesome
|  |  |
|  |  +--font-awesome.min.css
|  |  
|  +--fonts
|     |
|     +--fontawesome-webfont.woff2
|
+--assets
|  |
|  +--transparent.png
|  +--cursor-fa-eraser.cur
|  +--cursor-fa-pencil.cur
|
+--drawerJs
|  |  
|  +--drawerJs.min.css
|  +--drawerJs.css.map
|  +--drawerJs.standalone.js.min.js
|  +--drawerJs.standalone.js.map
|  +--drawerLocalization.js
|
+--images
|  |
|  +--drawer.jpg
|  
+--jQuery
|  |
|  +--jquery-1.10.1.min.js
|
+--drawerJsConfig.js
+--index.html
```

### Script: drawerJsConfig.js

```
var drawerPlugins = [
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
    'Color',
    'ShapeBorder',
    'BrushSize',
    'Resize',
    'ShapeContextMenu'
];
```

### Script: DrawerLocalization.js

```
var customLocalization = {
    'Add Drawer': 'Add Drawer',
    'Insert Drawer': 'Insert Drawer',
    'Insert': 'Insert',
    'Free drawing mode': 'Free drawing mode',
    'SimpleWhiteEraser': 'SimpleWhiteEraser',
    'Eraser': 'Eraser',
    'Delete this canvas': 'Delete this canvas',
    'Are you sure want to delete this canvas?': 'Are you sure want to delete this canvas?',
    
    // Canvas properties popup
    'Size (px)': 'Size (px)',
    'Position': 'Position',
    'Inline': 'Inline',
    'Left': 'Left',
    'Center': 'Center',
    'Right': 'Right',
    'Floating': 'Floating',
    'Canvas properties': 'Canvas properties',
    'Background': 'Background',
    'transparent': 'transparent',
    'Cancel': 'Cancel',
    'Save': 'Save',
    
    // Fullscreen plugin
    'Enter fullscreen mode': 'Enter fullscreen mode',
    'Exit fullscreen mode': 'Exit fullscreen mode',
    
    // Shape context menu plugin
    'Bring forward': 'Bring forward',
    'Send backwards': 'Send backwards',
    'Bring to front': 'Bring to front',
    'Send to back': 'Send to back',
    'Duplicate': 'Duplicate',
    'Remove': 'Remove',
    
    // Brush size plugin
    'Size:': 'Size:',
    
    // Color picker plugin
    'Fill:': 'Fill:',
    'Transparent': 'Transparent',
    // shape border plugin
    'Border:': 'Border:',
    'None': 'None',
    
    // Arrow plugin
    'Draw an arrow': 'Draw an arrow',
    'Draw a two-sided arrow': 'Draw a two-sided arrow',
    'Lines and arrows': 'Lines and arrows',
    
    // Circle plugin
    'Draw a circle': 'Draw a circle',
    
    // Line plugin
    'Draw a line': 'Draw a line',
    
    // Rectangle plugin
    'Draw a rectangle': 'Draw a rectangle',
    
    // Triangle plugin
    'Draw a triangle': 'Draw a triangle',
    
    // Polygon plugin
    'Draw a Polygon': 'Draw a Polygon',
    'Stop drawing a polygon': 'Stop drawing a polygon (esc)',
    'Click to start a new line': 'Click to start a new line',
    
    // Text plugin
    'Draw a text': 'Draw a text',
    'Click to place a text': 'Click to place a text',
    'Font:': 'Font:',
    
    // Movable floating mode plugin
    'Move canvas': 'Move canvas',
    
    // Base shape
    'Click to start drawing a ': 'Click to start drawing a '
};
```

* Initialization of DrawerJs: `new DrawerJs.Drawer(redactorInstance, options, width, height)`

    * Parameters: 
        * `redactorInstance`: 
            * Type: Object
            * Redactor's instance. Specify `null` for the standalone version 
        * `options`: 
            * Type: Object
            * Object with configuration parameters 
        * `width`:
            * Type: Number
            * Width in px 
        * height:
            * Type: Number
            * Height in px 

