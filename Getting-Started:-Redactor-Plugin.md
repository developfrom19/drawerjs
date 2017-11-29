####  A simple example of using DrawerJs as a Redactor plugin. 

***
### Adding to Site
```
<!DOCTYPE HTML>
<html>
    <head>
        <link rel="stylesheet" href="font-awesome/4.2.0/css/font-awesome.min.css" />
        <link rel="stylesheet" href="redactor/redactor.min.css" />
        <link rel="stylesheet" href="drawerJs/drawerJs.min.css" />
    </head>
    <body>
        <textarea class="redactor" cols="30" rows="10"></textarea>
        <script src="jQuery/jquery-1.10.1.min.js"></script>
        <script src="redactor/redactor.min.js"></script>
        <script src="drawerJs/drawerJs.redactor.min.js"></script>
        <script src="drawerJs/DrawerLocalization.js"></script>
        <script src="redactorConfig.js"></script>
        <script>
            $(document).ready(function () {
                $('.redactor').redactor(redactorConfig);
            });
        </script>
    </body>
</html>
```

### Script: redactorConfig.js
```
var redactorConfig = {
    plugins: ['drawer'],
    drawer: {
        texts: customLocalization,
        contentConfig: {
            saveAfterInactiveSec: 5,
            saveInHtml: true
        },
        plugins: [
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
            'Fullscreen',
            'MovableFloatingMode'
        ],
        pluginsConfig: {
            'Pencil': {
                 cursorUrl: 'pencil',
                 brushSize: 3
             },
             'Eraser': {
                 brushSize: 5
             },
             'Circle': {
                 centeringMode: 'normal'
             },
             'Rectangle': {
                 centeringMode: 'normal'
             },
             'Triangle': {
                 centeringMode: 'normal'
             },
             'Text': {
                 defaultFont: 'Palatino'
             },
             'ShapeContextMenu': {
                 position: {
                     touch: 'cursor',
                     mouse: 'cursor'
                }
            }
        }
    }
};
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
    
    // Shape border plugin
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