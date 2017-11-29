#### Provides an image tool for inserting images. 

***
### Enabling the Plugin
```
plugins: [
    'Image'
]
```
### Configuration
```
pluginsConfig: {
    'Image': {
        scaleDownLargeImage: true,
        maxImageSizeKb: 5120,
        acceptedMIMETypes: ['image/jpeg', 'image/png', 'image/gif'],
        cropIsActive: true
    }
}
```
The configuration example shows the default settings that are used if no configuration is provided.
* `scaleDownLargeImage`:
    * If set to `true` the inserted image is automatically scaled down to fit into canvas.
* `maxImageSizeKb`:
    * Sets the maximum size in KB of an image to be inserted. 
    * Settings of `null` or `0` will allow any size of image to be inserted. 
* `acceptedMIMETypes`:
    * Sets the allowed mime types to insert in canvas. 
* `cropIsActive`:
    * Allows cropping of image during insertion. 
    * For this feature the `ImageCrop` plugin is needed. 