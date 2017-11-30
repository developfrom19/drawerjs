#### Specifies styles that are applied to objects that are being created. 

***
### Configuration
```
drawer: {
    canvasProperties: {
        selectionColor: 'rgba(255, 255, 255, 0.3)',
        selectionDashArray: [3, 8],
        selectionBorderColor: '#5f5f5f',
        selectionLineWidth: 3
    }
}
```
* Optional setting. If not specified, the settings shown in the example will be used.
* `selectionColor`:
    * Specifies the color of the selection rectangle. 
* `selectionDashArray`:
    * Specifies the pattern to use for dashed selection lines. 
    * The first value represents the space between two dashes, the second one the length of the dashes themselves. 
* `selectionLineWidth`:
    * Specifies the selection line's width in pixels.
* `selectionBorderColor`:
    * Specifies the selection line's color.