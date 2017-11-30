#### Provides a tool for configuring border styles and colors. 

***
### Enabling the Plugin
```
plugins: [
    'ShapeBorder'
]
```
### Configuration
```
pluginsConfig: {
    'ShapeBorder': {
        color: 'rgba(0, 0, 0, 0)',
        defaultBorder: 'None'
    }
}
```
* `color`: 
    * Sets the default border color.
* `defaultBorder`:
    * The border style that will be applied when an object is being created.
    * Possible values are: 
        * `true`
        * `false`
        * `'None'`
        * `'Solid thin'`
        * `'Solid bold'`
        * `'Dashed thin'`
        * `'Dashed bold'`