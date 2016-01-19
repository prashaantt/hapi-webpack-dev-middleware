# hapi-webpack-dev-middleware

hapi plugin to use webpack-dev-middleware, possibly in conjunction with [hapi-webpack-hot-middleware](https://github.com/prashaantt/hapi-webpack-hot-middleware). 

[![Dependency Status](https://david-dm.org/prashaantt/hapi-webpack-dev-middleware.svg)](https://david-dm.org/prashaantt/hapi-webpack-dev-middleware)
[![devDependency Status](https://david-dm.org/prashaantt/hapi-webpack-dev-middleware/dev-status.svg?theme=shields.io)](https://david-dm.org/prashaantt/hapi-webpack-dev-middleware#info=devDependencies)


## Installation

```bash
$ npm install hapi-webpack-dev-middleware --save-dev
```


## Usage

Require and register normally as a hapi plugin:

```js
server.register(
    {
        register: require('hapi-webpack-dev-middleware'),
        options: {
            config: require('./webpack.config.js'),
            options: {
                noInfo: true,
                publicPath:  '/static'
            }
        }
    }
);
```

Configuration options:

- ```config```: The Webpack config to use.
- ```options```: The options you'd normally pass to ```webpack-dev-middleware```. Refer to their [documentation](https://github.com/webpack/webpack-dev-middleware) for all possible values.

**Note: This plugin adds the ```webpackCompiler``` object to the ```server.app``` namespace to share it with any other plugins such as [hapi-webpack-hot-middleware](https://github.com/prashaantt/hapi-webpack-hot-middleware) that depend on the same compiler being available to them.** 


## License

MIT
