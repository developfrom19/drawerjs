#### Specifies the default plugin that will be used initially when activating edit mode (clicking on canvas element). 

***
### Configuration
```
drawer: {
   defaultPlugin: {
       name: 'Pencil',
       mode: 'onNew'
   }
}
```
* Optional setting. If not specified, no default plugin will be used.
* `name`:
    * Specifies the name of the plugin to activate automatically when edit mode is started. 
    * Possible values: 
        * All configured plugins (Drawing Tools): 
            * 'Pencil'
            * 'Eraser'
            * 'Text'
            * 'Line'
            * 'ArrowOneSide'
            * 'ArrowTwoSide'
            * 'Triangle'
            * 'Rectangle'
            * 'Circle'
            * 'Polygon'
* `mode`:
    * Specifies when the default plugin is used. 
    * Possible values: 
        * `onNew`
            * Default plugin is only used for the first time the edit mode is activated. 
        * `always`
            * Default plugin is used every time the edit mode is activated. 
        * `lastUsed`
            * Default plugin is only used for the first time the edit mode is activated. 
            * For all subsequent edit modes the last used plugin is used automatically. 