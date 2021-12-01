# com.creative-scripts.drag.and.drop

The drag & drop works on Windows CEP Panel.  
On the Mac it cannot be dragged in the Panel.
It can be dragged in the CEP debug port `7042` and syncs with the panel.
In the App.vue localhost it drags but is not synced with the panel.

## Project setup

Make a symlink to the extension folder

```
sudo ln -s /PATH/TO/REPO/drag-drop-public/com.creative-scripts.drag.and.drop /Library/Application\ Support/Adobe/CEP/extensions/com.creative-scripts.drag.and.drop
```

```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Open Illustrator
Go to Windows > Extensions > com.creative-scripts.drag.and.drop

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
