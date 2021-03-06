####  Provides a color picker for changing the color of shapes and freehand drawings. 

***
### Enabling the Plugin
```
drawer: {
    activeColor: '#19A6FD',
    plugins: [
        'Color'
    ]
}
```
### Configuration
```
pluginsConfig: {
    'Color': {
        colors: [
            '#ffffff', '#000000', '#eeece1', '#1f497d', '#4f81bd', '#c0504d',
            '#9bbb59', '#8064a2', '#4bacc6', '#f79646', '#ffff00',
            '#f2f2f2', '#7f7f7f', '#ddd9c3', '#c6d9f0', '#dbe5f1', '#f2dcdb',
            '#ebf1dd', '#e5e0ec', '#dbeef3', '#fdeada', '#fff2ca',
            '#d8d8d8', '#595959', '#c4bd97', '#8db3e2', '#b8cce4', '#e5b9b7',
            '#d7e3bc', '#ccc1d9', '#b7dde8', '#fbd5b5', '#ffe694',
            '#bfbfbf', '#3f3f3f', '#938953', '#548dd4', '#95b3d7', '#d99694',
            '#c3d69b', '#b2a2c7', '#b7dde8', '#fac08f', '#f2c314',
            '#a5a5a5', '#262626', '#494429', '#17365d', '#366092', '#953734',
            '#76923c', '#5f497a', '#92cddc', '#e36c09', '#c09100',
            '#7f7f7f', '#0c0c0c', '#1d1b10', '#0f243e', '#244061', '#632423',
            '#4f6128', '#3f3151', '#31859b', '#974806', '#7f6000'
        ],
        colorsInRow: 11
    }
}
```
The configuration example shows the default settings that are used if no configuration is provided.
* `activeColor`:
    * Specifies the color picker's default color that is preselected when DrawerJs is initialized.
    * Optional setting. If not set, the default color shown in example is used.
* `colors`: 
    * Defines all usable colors.
* `colorsInRow`:
    * Defines the number of colors per row.
