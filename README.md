# reapop-theme-wybo

Official theme for [Reapop](https://github.com/LouisBarranqueiro/reapop) 

## Installation

``` js
npm install reapop-theme-wybo --save
```

## Integration

``` js
import React, {Component} from 'react';
import NotificationsSystem from 'reapop';
// 1. import theme
import theme from 'react-theme-wybo';
// 
class ATopLevelComponent extends Component {
  render() { 
   // 2. set `theme` prop
    return (
      <div>
        <NotificationsSystem theme={theme}/>
      </div>
    );
  }
}
```

## License 

Reapop-theme-wybo is under [GPL-3.0 License](https://github.com/LouisBarranqueiro/reapop/blob/master/LICENSE)