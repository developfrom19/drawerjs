### Configuration in drawer

#### Specifies the size of toolbar buttons. 

***
```
drawer: {
    toolbarSize: 35,
    toolbarSizeTouch: 43
}
```
* Optional setting. If not specified, the settings shown in the example will be used.
* `toolbarSize`:
    * Specifies the size in px of DrawerJs' toolbar buttons when running on non-touch devices.
* `toolbarSizeTouch`:
    * Specifies the size in px of DrawerJs' toolbar buttons when running on touch devices.

### Configuration of toolbars

#### Specifies appearance and behavior of toolbars. 
```
toolbars: {
    drawingTools: {
        position: 'top',         
        positionType: 'outside',
        customAnchorSelector: '#custom-toolbar-here',  
        compactType: 'scrollable',   
        hidden: false,     
        toggleVisibilityButton: false,
        fullscreenMode: {
            position: 'top', 
            hidden: false,
            toggleVisibilityButton: false
        }
    },
    toolOptions: {
        position: 'bottom', 
        positionType: 'outside',
        compactType: 'multiline',        
        hidden: false,
        toggleVisibilityButton: false,
        fullscreenMode: {
            position: 'bottom', 
            compactType: 'popup',
            hidden: false,
            toggleVisibilityButton: false
        }
    },
    settings: {
        position: 'right',
        positionType: 'outside',   
        compactType: 'scrollable',            
        hidden: false,
        toggleVisibilityButton: false,
        fullscreenMode: {
            position: 'right', 
            hidden: false,
            toggleVisibilityButton: false
        }
    }
}
```
* Optional settings. If not specified, the settings shown in the example will be used.
* `position`:
    * Specifies the position of each `toolbar`.
        * Defines the placement of: 
            * `'left'`: Places the toolbar to the left side of DrawerJs' canvas element. 
            * `'right'`: Places the toolbar to the right side of DrawerJs' canvas element. 
            * `'top'`: Places the toolbar to the top of DrawerJs' canvas element. 
            * `'bottom'`: Places the toolbar to the bottom of DrawerJs' canvas element. 
            * `'custom'`: Places the toolbar to any HTML element on the website with the Id of setting `customAnchorSelector`.  
This setting greatly depends on CSS of wrapping container. 
* `positionType`:
    * Specifies where toolbar is shown related to canvas.
    * `inside`: Will show toolbar above canvas.
    * `outside`: Will show toolbar outside of canvas.
* `customAnchorSelector`: 
    * Defines the Id of the HTML anchor. 
    * This setting can only be used with `position` setting set to `'custom'`. 
* `compactType`:
    * Specifies the appearance of each toolbar when width is smaller than needed. 
        * `'scrollable'`: Shows arrows at left and right side of toolbar to enable scrolling of tools.
        * `'multiline'`: Stack tools.
        * `'popup'`:
            * Only available for `toolOptions`.
            * Will show a popup menu on canvas when an object or a plugin is selected. 
            * Needed plugins: 'OvercanvasPopup', 'OpenPopupButton'. 
* `hidden`:
    * Specifies if toolbar is hidden.
    * Needed for custom toolbars which can be invoked instead.
    * Possible values are: `true` or `false`.
* `toggleVisibilityButton`:
    * Enables toggling between each toolbar set to `true`.
    * Needed plugin: 'ToggleVisibilityButton'
    * Possible values are: `true` or `false`.
* `fullscreenMode`:
    * Specifies behavior when DrawerJs is in fullscreen mode.
    * Needed plugin: 'FullscreenModeButton'
    * `positionType`: This can not be set in fullscreen mode. It is always set to `inside` by default. 
    * `position`: Specifies the setting only when DrawerJs is shown in fullscreen mode.
    * `hidden`: Specifies the setting only when DrawerJs is shown in fullscreen mode.
    * `toggleVisibilityButton`: Specifies the setting only when DrawerJs is shown in fullscreen mode.

* Available states of toolbar:
    * `Overlay`: Overlay of placeholder is visible
    * `Disabled`: visible, but not clickable 
    * `Hidden` : invisible 
* Plugins affected with this functionality: 
    * ImageCrop: - "Hidden" state is used 
    * OvercanvasPopup: "Overlay" state is used 

### Plugins: Ordering of Toolbar Position

#### Specifies the order of toolbar buttons. 

***
```
pluginsConfig: {
    'Circle': {
        centeringMode: 'normal'
    },
    buttonOrder: 10
}
```
* Optional setting. If not specified, the settings shown in the example will be used.
* Option for all plugins that have toolbar `buttons` or `options`.
* Button with min `buttonOrder` value will be displayed as first button