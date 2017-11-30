#### Provides a tool to draw triangles. 

***
### Enabling the Plugin
```
plugins: [
    'Triangle',
    'Color',
    'ShapeBorder'
]
```
###  Configuration
```
pluginsConfig: {
    'Triangle': {
        centeringMode: 'normal'
    }
}
```
* `centeringMode`: 
    * Defines the centering method when drawing a triangle: 
        * `'normal'`: The top left corner of the rectangular box around the triangle will be placed at the position of the first mouse click. The triangle will be resized from that point. 
        * `'from_center'`: The top left corner of the rectangular box around the triangle will be placed at the position of the first mouse click. The triangle will be resized from that point. 
* The _Color_ or _ColorHtml5_ plugin allows the user to set the color of the shape. 
* The optional _ShapeBorder_ plugin allows the user to set the color and style of the border. 
