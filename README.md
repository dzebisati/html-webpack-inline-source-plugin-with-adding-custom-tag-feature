
html-webpack-inline-source-plugin with custom script tag attributes
========================================

Fork of [html-webpack-inline-source-plugin](https://github.com/DustinJackson/html-webpack-inline-source-plugin) by
[Dustin Jackson](https://github.com/DustinJackson)

Fork features
------------
Too add custom attribute to script tag, in your webpack configuration file
invoke function 

Install the plugin with npm:
```javascript
const myCustomAttributes = {
    "YourCustomAttribute": 'value',
     // ... More attributes  
};

//...
new HtmlWebpackInlineSourcePlugin(HtmlWebpackPlugin, myCustomAttributes),
//...
```

This is an extension plugin for the [webpack](http://webpack.github.io) plugin [html-webpack-plugin](https://github.com/ampedandwired/html-webpack-plugin) (version 4 or higher).  It allows you to embed javascript and css source inline.

Installation
------------
You must be running webpack on node 6 or higher.

Install the plugin with npm:
```shell
$ npm install --save-dev html-webpack-inline-source-plugin
```

Basic Usage
-----------
Require the plugin in your webpack config:

```javascript
var HtmlWebpackInlineSourcePlugin = require('html-webpack-inline-source-plugin');
```

Add the plugin to your webpack config as follows:

```javascript
plugins: [
  new HtmlWebpackPlugin(),
  new HtmlWebpackInlineSourcePlugin()
]  
```
The above configuration will actually do nothing due to the configuration defaults.

When you set `inlineSource` to a regular expression the source code for any javascript or css file names that match will be embedded inline in the resulting html document.
```javascript
plugins: [
  new HtmlWebpackPlugin({
		inlineSource: '.(js|css)$' // embed all javascript and css inline
	}),
  new HtmlWebpackInlineSourcePlugin()
]  
```

Sourcemaps
----------
If any source files contain a sourceMappingURL directive that isn't a data URI, then the sourcemap URL is corrected to be relative to the domain root (unless it already is) instead of to the original source file.

All sourcemap comment styles are supported:

* `//# ...`
* `//@ ...`
* `/*# ...*/`
* `/*@ ...*/`
