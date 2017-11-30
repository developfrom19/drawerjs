####  Provides a tool to draw rectangles. 

***
### Enabling the Plugin
```
plugins: [
    'Rectangle',
    'Color',
    'ShapeBorder'
]
```
### Configuration
```
pluginsConfig: {
    'Rectangle': {
        centeringMode: 'normal'
    }
}
```
* `centeringMode`:
    * Defines the centering method when drawing a rectangle: 
        * `'normal'`: The rectangle's top left corner will be placed at the position of the first mouse click and will be resized from that point. 
        * `'from_center'`: The rectangle's top left corner will be placed at the position of the first mouse click and will be resized from that point. 
* The Color or _ColorHtml5_ plugin allows the user to set the color of the shape. 
* The optional _ShapeBorder_ plugin allows the user to set the color and style of the border. 