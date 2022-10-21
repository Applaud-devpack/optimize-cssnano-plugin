# @applaud/optimize-cssnano-plugin [![Build Status](https://travis-ci.org/intervolga/optimize-cssnano-plugin.svg?branch=master)](https://travis-ci.org/intervolga/optimize-cssnano-plugin)

It will search for CSS assets during the Webpack build and minimize it with [cssnano](https://github.com/Applaud-devpack/cssnano).
Solves [extract-text-webpack-plugin](http://github.com/webpack/extract-text-webpack-plugin) CSS duplication problem.

Just like [optimize-css-assets-webpack-plugin](http://github.com/NMFR/optimize-css-assets-webpack-plugin) but more accurate with source maps.

## Installation:

Using npm:
```shell
$ npm install --save-dev @applaud/optimize-cssnano-plugin
```

## Configuration:

``` javascript
const OptimizeCssnanoPlugin = require('@applaud/optimize-cssnano-plugin');
module.exports = {
	module: {
		loaders: [
			{ test: /\.css$/, loader: ExtractTextPlugin.extract("style-loader", "css-loader") }
		]
	},
	plugins: [
    new ExtractTextPlugin("styles.css"),

    new OptimizeCssnanoPlugin({
      sourceMap: nextSourceMap,
      cssnanoOptions: {
        preset: ['default', {
          discardComments: {
            removeAll: true,
          },
        }],
      },
    }),
	]
}
```

<h2 align="center">Maintainers</h2>

<table>
  <tbody>
    <tr>
      <td align="center">
        <a href="https://github.com/Applaud-devpack">
          <img width="150" height="150" src="https://github.com/Applaud-devpack.png?v=3&s=150">
          </br>
          Applaud Dev team
        </a>
      </td>
    </tr>
  <tbody>
</table>
