# reapop-theme-wybo

## :warning: This package is deprecated because this theme is now directly included in the lastest version of [reapop](https://github.com/LouisBarranqueiro/reapop) package. 

[![npm version](https://img.shields.io/npm/v/reapop-theme-wybo.svg?style=flat-square)](https://www.npmjs.com/package/reapop-theme-wybo) [![npm dependencies](https://img.shields.io/david/LouisBarranqueiro/reapop-theme-wybo.svg?style=flat-square)](https://www.npmjs.com/package/reapop-theme-wybo) [![npm download/month](https://img.shields.io/npm/dm/reapop-theme-wybo.svg?style=flat-square)](https://www.npmjs.com/package/reapop-theme-wybo) [![gitter chat](https://img.shields.io/gitter/room/LouisBarranqueiro/reapop-theme-wybo.svg?style=flat-square)](https://gitter.im/LouisBarranqueiro/reapop-theme-wybo)

Official theme for [Reapop](https://github.com/LouisBarranqueiro/reapop)

## Compatibility

Tested and works with **Reapop v0.6.0 or later** in :

### Supported browsers

| [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/edge/edge_48x48.png" alt="IE / Edge" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>IE / Edge | [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/firefox/firefox_48x48.png" alt="Firefox" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>Firefox | [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/chrome/chrome_48x48.png" alt="Chrome" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>Chrome | [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/safari/safari_48x48.png" alt="Safari" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>Safari | [<img src="https://raw.githubusercontent.com/alrra/browser-logos/master/src/opera/opera_48x48.png" alt="Opera" width="24px" height="24px" />](http://godban.github.io/browsers-support-badges/)</br>Opera |
| --------- | --------- | --------- | --------- | --------- |
| IE10, IE11, Edge| last 2 versions| last 2 versions| last 2 versions| last 2 versions

## Installation

```
npm install reapop-theme-wybo --save
```

## Integration

### Update webpack config

You have to define some loaders to handle files of theme. If it's not already the case, you need to install :

 - **style-loader** with `npm install style-loader --save-dev`
 - **css-loader** with `npm install css-loader --save-dev`
 - **url-loader** with `npm install url-loader --save-dev`
 - **file-loader** with `npm install file-loader --save-dev`

Look at this example, you can use it in for your project. Check out configuration of [Reapop Demo](https://github.com/LouisBarranqueiro/reapop) to see a complete example.

``` js
// CSS loader with some configuration
// read https://github.com/webpack/css-loader to understand each query parameters
var CSSLoader = [
  'css-loader?sourceMap&-minimize',
  'modules',
  'importLoaders=1',
  'localIdentName=[name]__[local]__[hash:base64:5]'
].join('&');

module.exports = {
  module: {
    loaders: [{
      test: /\.css$/,
      loaders: ['style-loader', CSSLoader]
    }, {
      test: /\.woff(2)?(\?v=[0-9]\.[0-9]\.[0-9])?$/,
      loader: "url-loader?limit=10000&minetype=application/font-woff"
    }, {
      test: /\.(ttf|eot|svg)(\?v=[0-9]\.[0-9]\.[0-9])?$/,
      loader: "file-loader"
    }]
  }
};
```

### Install Font Awesome

This theme doesn't include Font Awesome to let you install it the way you want:

#### With Webpack

1. Install Font Awesome with `npm install font-awesome --save`

and import it in your app. Example :

```
import '!style-loader!css-loader!font-awesome/css/font-awesome.min.css';
```

#### With BootstrapCDN

Add this line in `<head>` of your main `index.html` file :
``` html
<link href="https://maxcdn.bootstrapcdn.com/font-awesome/4.6.3/css/font-awesome.min.css" rel="stylesheet">
```


### Set the theme

``` js
import React, {Component} from 'react';
import NotificationsSystem from 'reapop';
// 1. import Font Awesome
import '!style-loader!css-loader!font-awesome/css/font-awesome.min.css';
// 2. import reapop theme
import theme from 'reapop-theme-wybo';

class ATopLevelComponent extends Component {
  render() {
   // 3. set `theme` prop
    return (
      <div>
        <NotificationsSystem theme={theme}/>
      </div>
    );
  }
}
```

### Customize the theme

Follow this guide : [Reapop - Customize or create a theme](https://github.com/LouisBarranqueiro/reapop/blob/master/docs/api.md#customize-or-create-a-theme)


## License

Reapop-theme-wybo is under [MIT License](https://github.com/LouisBarranqueiro/reapop-theme-wybo/blob/master/LICENSE)
