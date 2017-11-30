#### Option needed when binaries are placed in different location as DrawerJs' assets.

***
### Configuration
```
drawer: {
    basePath: '/Client/scripts/vendor/DrawerJs'
}
```
* Optional setting. If not specified otherwise, DrawerJs tries to find the folder from which the script is included (script tag in HTML markup). 
* Path is used e.g. for default image: Specifies the location of the default image that will be drawn initially within the DrawerJs container. 
* For example the base path setting is needed when DrawerJs is used in a ASP.NET MVC application. 

**Example**  
Domain: example.com 

Location of DrawerJs:  
drawerJs.standalone.js in _/js/vendor/drawer_

Location of Assets:  
e.g. cursor-fa-eraser.cur, cursor-fa-pencil.cur, etc. in _/img/vendor/drawer/assets_

In this case this option needs to be set: basePath: `'http://example.com/img/vendor/drawer/'`