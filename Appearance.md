#### Customizes the background, border style, and initial size of the DrawerJs canvas. 

***
### Configuring Background and Border Styles
```
borderCss: '1px dashed rgb(195, 194, 194)',
borderCssEditMode: '1px dashed rgb(195, 194, 194)',
backgroundCss: 'transparent'

```
 All settings are optional. If not specified otherwise, the above defaults will be used. 
* `borderCss`:
    * Specifies the CSS `border` property of the canvas that is applied to displayed drawings.
* `borderCssEditMode`:
    * Specifies the CSS `border` property that is applied while editing a drawing.
* `backgroundCss`:
    * Specifies the CSS `background` property of the canvas container.
    * Examples:
        * `'url(/assets/transparent.png) repeat'`
        * `'transparent'`
### Specifying the Size of the Standalone Version
```
var drawer = new DrawerJs.Drawer(null, {
    texts: CustomLocalization,
    plugins: drawerPlugins,
    defaultImageUrl: '/images/drawer.jpg'
}, 600, 600);
```
* `new DrawerJs.Drawer(redactorInstance, options, width, height)`
    * Parameters:
        * `redactorInstance`:
            * Type: Object 
            * Redactor's instance. Specify `null` for the standalone version. 
        * `options`:
            * Type: Object 
            * Object with configuration parameters. 
        * `width`:
            * Type: Number 
            * Width in px. 
        * `height`:
            * Type: Number 
            * Height in px. 