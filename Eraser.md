####  Provides an eraser tool which can be used to erase any drawing or shape. 

***
### Enabling the Plugin
```
plugins: [
    'Eraser',
    'BrushSize'
]
```
### Configuration
```
pluginsConfig: {
    'Eraser': {
        cursorUrl: 'url(assets/eraser_cursor.cur), default',
        brushSize: 3
    }
}
```
* `cursorUrl`:
    *  Optional property that can be set to use the cursor from the specified file.  
 The URL is specified in typical CSS format: `'url(assets/eraser_cursor.cur), default'` 
    * Note the word `default` at the end: that is the name of the cursor that will be used when the specified URL is unavailable.  
The Mozilla Developer Network has more information on the [CSS cursor property](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor). 
* `brushSize`:
    * Sets the default brush size. 
    * If you want the user to be able to set their own brush size, the _BrushSize_ plugin must be included, too. 