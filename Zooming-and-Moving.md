#### Enables zooming in canvas. And once zooming is active, moving canvas can be used, too. 

***
Touch gestures: 
* Pinch and spread for zoom in and zoom out. 
* Tap and drag for moving canvas. 
### Enabling the Plugin
```
plugins: [
    'Zoom'
]
```
### Configuration of Zoom Feature
```
drawer: {
    Zoom: {
        enabled: true,
        showZoomTooltip: true,
        useWheelEvents: true,
        zoomStep: 1.05,
        defaultZoom: 1,
        maxZoom: 32,
        minZoom: 1,
        smoothnessOfWheel: 0
    }
}
```
Optional setting. If not specified otherwise, the settings shown in the example will be used.
* `enabled`:
    * Enables or disables the zooming feature. 
* `showZoomTooltip`:
    * Show tooltip with current zoom value on any change of zoom level. 
* `useWheelEvents`:
    * Enables or disables zooming using mousewheel. 
* `zoomStep`:
    * Step size for each zoom change (1.05 = 105%). 
* `defaultZoom`:
    * Default value of zoom. 
* `maxZoom`:
    * Maximum zoom level (32 = 3200%). 
* `minZoom`:
    * Minimum zoom level (1 = 100%). 
* `smoothnessOfWheel`:
    * Sets the font size of the tooltip. 
    * Value 0: Point of zoom center is never changed when using mouse wheel. 
    * Value 1: Point of zoom center will be moved when using mouse wheel. 
    * This option has a default value of 0.1. 
### Configuration of Move Feature
```
drawer: {
    Zoom: {
        enableMove: true,
		enableWhenNoActiveTool: true,
		enableButton: true
    }
}
```
Optional setting. If not specified otherwise, the settings shown in the example will be used.
* `enableMove`:
    * Enables or disables the moving feature. 
* `enableWhenNoActiveTool`:
    * When set to `true` it is only allowed to move canvas when no object is selected and no tool is active (selected). 
    * This means the moving feature and its icon will be active when no object is selected nor any tool is selected from toolbar. 
* `enableButton`:
    * When set to `true` a button is added to settings toolbar. 
    * This button shows moving status: Button is active when canvas can be moved. 
### Combination of these settings
When options `enableWhenNoActiveTool` and `enableButton` are enabled, the move button will automatically turns active after any tool is deactivated or object is deselected.  

When only `enableButton` is set to `true`, the user is able to move the canvas only after clicking on _Move Canvas_ 
button. 

When both options are disabled, the moving feature is not useable, even `enableMove` is set to `true`. 