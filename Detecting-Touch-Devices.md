#### Specifies the function that DrawerJs calls to determine whether it's running on a touch device. 

***
### Configuration
```
detectTouch: function() {
    // Your code goes here
}

```
* This function must return `true` or `false`.
* If the function returns `true`, DrawerJs assumes it runs on a touch device and will … 
    * adjust its toolbar size (see property _toolbarSizeTouch_)
    * adjust its context menu size
    * use touch-optimized settings for object control (see property _objectControlsTouch_)
    * add touch events
* If this function is not specified explicitly, DrawerJs will use its own touch detection mechanism. 
### Disabling Touch Detection
To disable touch detection entirely, simply return `false` from the `detectTouch` function:
```
detectTouch: function() {
    return false;
}
```
