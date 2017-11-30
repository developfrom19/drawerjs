####  Provides a pencil tool for freehand drawing. 

***
### Enabling the Plugin
```
plugins: [
    'Pencil',
    'BrushSize'
]
```
### Configuration
```
pluginsConfig: {
    'Pencil': {
        cursorUrl: 'pencil',
        brushSize: 3
    }
}
```
* `cursorUrl`:
    * `'pencil'` is a default icon built into DrawerJs.
    * You can also specify a custom cursor URL in CSS format: `url(assets/eraser_cursor.cur), defaul`
    * Note the word `default` at the end: that is the name of the cursor that will be used when the specified URL is unavailable.  
The Mozilla Developer Network has more information on the [CSS cursor property](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor). 
* `brushSize`: 
    * Sets the default brush size. 
    * If you want the user to be able to set their own brush size, the _BrushSize_ plugin must be included, too. 