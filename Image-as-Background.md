#### Provides an image tool for inserting or configuring images to show as canvas' background. 

***
Enabling the Plugin
```
plugins: [
    'BackgroundImage'
]
```
### Configuration
```
pluginsConfig: {
    'BackgroundImage': {
        scaleDownLargeImage: true,
        maxImageSizeKb: 5120,
        acceptedMIMETypes: ['image/jpeg', 'image/png', 'image/gif'],
        imagePosition: 'stretch',
        dynamicRepositionImage: true,
        dynamicRepositionImageThrottle: 100,
        fixedBackgroundUrl: '/images/yourImage.jpg',
        cropIsActive: true
    }
}
```
The configuration example shows the default settings (except `fixedBackgroundUrl`) that are used if no configuration is provided.  
This plugin supports two modes: you can show the users an icon in the toolbar so they can upload an image for using it as a background themselves.  

Or you add the setting `fixedBackgroundUrl` to define an image as a fixed background. In this case the icon in toolbar is not shown. 
#### Mode 1: User can upload an image 
 This mode gets activated by omitting the setting `fixedBackgroundUrl` from your configuration.
* `maxImageSizeKb`:
    * Sets the maximum size in KB of an image to be inserted. 
    * Settings of `null` or `0` will allow any size of image to be inserted. 
* `acceptedMIMETypes`:
    * Sets the allowed mime types to insert in the canvas. 
#### Mode 2: Background Image is pre-configured 
This mode gets activated by adding the setting `fixedBackgroundUrl` and define the location of the image.  
* `fixedBackgroundUrl`:
    * Here you can define an URL to your image. This can be a http path or a path to a file on your disk.
#### Configuration for both modes 
These settings are available for both modes. 
* `imagePosition`
    * You can set this to one of these options: 
        * `stretch`: Will stretch the image to the whole canvas. 
        * `center`: Will center the image on the canvas. 
        * `top-left`: Will place the image on the top-left of the canvas. 
        * `top-right`: Will place the image on the top-right of the canvas. 
        * `bottom-left`: Will place the image on the bottom-left of the canvas. 
        * `bottom-right`: Will place the image on the bottom-right of the canvas. 
* `scaleDownLargeImage`: 
    * If set to `true` the inserted image is automatically scaled down to fit into the canvas.
* `dynamicRepositionImage`: 
    * If set to `true` the background image is dynamically and smoothly resized while the canvas gets resized. 
    * If set to `false` the background image is resized to fit into the canvas after resizing of canvas has been finished. 
* `dynamicRepositionImageThrottle`
    * Only used if `dynamicRepositionImage` is set to `true`. 
    * This setting defines the throttle time in ms for resizing. 
    * If set to `0` no throttling is used and the image is resized on every mouse move while resizing the canvas. 
    * Example: `200` means that resizing of background image will occur once every 200ms. This option greatly reduces CPU load during resize of the canvas with a background image. 
* `cropIsActive`:
    * Allows cropping of image during insertion. 
    * For this feature the `ImageCrop` plugin is needed. 