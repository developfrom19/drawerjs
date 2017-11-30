#### Provides a context menu for moving shapes to the background/foreground, duplicating them, or removing them.

***
### Enabling the Plugin
```
plugins: [
    'ShapeContextMenu'
]
```
### Configuration
```
pluginsConfig: {
    'ShapeContextMenu': {
        position: {
            touch: 'shapeRightBottom',
            mouse: 'cursor'
        },
        customMenuRenderer : contextMenuCustomRenderer
    }
}
```
* `position`:
    * Type: object
    * `touch`:
        * Defines the placement of the context menu when working on touch devices.
        * Default: `'shapeRightBottom'`
    * `mouse`:
        * Defines the placement of the context menu when working on non-touch devices.
        * Default: `'cursor'`
    * Possible values are: 
        * `'cursor'`: The context menu will be placed at the position of the click.
        * `'shapeRightBottom'`: The context menu will be placed at the right bottom corner of the shape.
* `customMenuRenderer`:
    * Specifies a function that will be called when context menu is triggered. 
    * If a function is defined, no built-in context menu will be shown. 
    * Perfect to render a custom menu on touch devices to show options for shape handling, e.g. an ActionSheet. 
    * Default value is `null`. 