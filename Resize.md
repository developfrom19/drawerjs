#### Provides a tool for resizing the DrawerJs container. 

***
### Enabling the Plugin
```
plugins: [
    'Resize'
]
```
### Configuration
```
.redactor-drawer-resizer .resizer-box {
    height: 10px;
    width: 10px;
    background: rgb(92, 92, 92);
    cursor: nwse-resize;
}
```
* Configuring the plugin is currently not supported using DrawerJs' configuration system. 
* However, you can customize the resizer box in the lower right corner of the DrawerJs container by overwriting the CSS rule shown in the above sample. 