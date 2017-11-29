####  Provides a tool for adding text to a drawing. 

***
### Enabling the Plugin
```
plugins: [
    'Text',
    'Color',
    'TextLineHeight',
    'TextAlign',
    'TextFontFamily',
    'TextFontSize',
    'TextFontWeight',
    'TextFontStyle',
    'TextDecoration',
    'TextColor',
    'TextBackgroundColor'
]
```
### Configuration
```
pluginsConfig: {
    'Text': {
        fonts: {
            'Georgia': 'Georgia, serif',
            'Palatino': "'Palatino Linotype', 'Book Antiqua', Palatino, serif",
            'Times New Roman': "'Times New Roman', Times, serif",
            'Arial': 'Arial, Helvetica, sans-serif',
            'Arial Black': "'Arial Black', Gadget, sans-serif",
            'Comic Sans MS': "'Comic Sans MS', cursive, sans-serif",
            'Impact': 'Impact, Charcoal, sans-serif',
            'Lucida Grande': "'Lucida Sans Unicode', 'Lucida Grande', sans-serif",
            'Tahoma': 'Tahoma, Geneva, sans-serif',
            'Trebuchet MS': "'Trebuchet MS', Helvetica, sans-serif",
            'Verdana': 'Verdana, Geneva, sans-serif',
            'Courier New': "'Courier New', Courier, monospace",
            'Lucida Console': "'Lucida Console', Monaco, monospace"
        },
        defaultFont: 'Palatino',
        editIconMode : true,
        editIconSize : 'medium',
        defaultValues: {
            fontSize: 72,
            lineHeight: 2,
            textFontWeight: 'bold'
        },
        predefined: {
            fontSize: [8, 12, 14, 16, 32, 40, 72],
            lineHeight: [1, 2, 3, 4, 6]
       }
    }
}
```
* `fonts`: 
    * Type: Object. 
    * The keys of the object are font names which are displayed as a list.  
The corresponding values hold the values for the CSS `font-family` property. 
* `defaultFont`:
    * The default font that is selected when an object is being edited.
* `editIconMode`:
    * Type: Boolean. 
    * If set to `true` an edit symbol is shown above each text box and the default behaviour to edit a text while clicking in text box is disabled.
    * This feature will be mostly used on touch devices due some problems recognizing a tap gesture on text box.
* `editIconSize`:
    * Type: String. 
    * If `editIconMode` is set to `true` you can set the size of the edit symbol: 
        * `small`
        * `medium`
        * `large`
* The _Color_ or _ColorHtml5_ plugin allows the user to specify the text color. 
* `predefined`:
    * Optional setting. If not specified, the settings shown in the example will be used. 
    * List of available values for control settings via dropdown in UI. 
    * Type: Object. 
        * `fontSize` is a array with available font size numbers.
        * `lineHeight`  is a array with available line height numbers.
* `defaultValues`:
    * Optional setting. If not specified, the settings shown in the example will be used. 
    * List of default values of styles.
    * Type: Object. 
        * `fontSize` is an integer for default font size.
        * `lineHeight` is an integer for default line height.
        * `textFontWeight` is a string for default font weight.