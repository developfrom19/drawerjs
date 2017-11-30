#### Adds a button to the toolbar for going fullscreen. 

***
### Enabling the Plugin
```
plugins: [
    'FullscreenModeButton'
]
```
* Note that Fullscreen API only works during user interaction (click, keypress, etc.).
* For security reasons accessing full screen requires the user's "permission", and so is tied to browser input events.
* It will work inside click/keypress/input events handlers, but can't be used without them.  
Check this: https://wiki.mozilla.org/Gecko:FullScreenAPI#Suggested_UA_Policy  
Otherwise, requestFullScreen outside a user action (e.g. a non-synthesized input event handler) is denied. 