####  Provides a tool for drawing circles. 

***
### Enabling the Plugin
```
plugins: [
    'Circle',
    'Color',
    'ShapeBorder'
]
```
### Configuration
```
pluginsConfig: {
    'Circle': {
        centeringMode: 'normal'
    }
}
```
* `centeringMode`:
    * Defines the centering method when drawing a circle: 
        * `'normal'`: The circle's top left corner will be placed at the position of the first mouse click and will be resized from that point. 
        * `'from_center'`: The circle's center will be placed at the position of the first mouse click and will be resized from that point. 
* The _Color or ColorHtml5_ plugin allows the user to set the color of the shape. 
* The optional _ShapeBorder_ plugin allows the user to set the color and style of the border. 
