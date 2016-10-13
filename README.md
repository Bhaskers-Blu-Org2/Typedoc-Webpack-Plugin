[![npm version](https://img.shields.io/npm/v/typedoc-webpack-plugin.svg)](https://www.npmjs.com/package/typedoc-webpack-plugin)
[![Downloads](https://img.shields.io/npm/dm/typedoc-webpack-plugin.svg)](https://www.npmjs.com/package/typedoc-webpack-plugin)

# Typedoc-Webpack-Plugin
This is a plugin for the Webpack build system that will run Typedoc in order to generate API documentation.

To use, add a require for the module to the Webpack Configuration file, and then place into the plugin section:


```
var TypedocWebpackPlugin = require('typedoc-webpack-plugin');

...

plugins: [
	new TypedocWebpackPlugin({})
]
```


The options for the plugin mirror the options that are passed to typedoc. Refer to https://github.com/TypeStrong/typedoc for full options. 

The default options that are set by the plugin are:

```
{
	out: './docs',
	module: 'commonjs',
	target: 'es5',
	exclude: '**/node_modules/**/*.*',
	experimentalDecorators: true,
	excludeExternals: true
}
```


Here is an example of a more expanded configuration:

```
plugins: [
	new TypedocWebpackPlugin({
		name: 'Contoso'
		mode: 'file',
		theme: './typedoc-theme/',
		includeDeclarations: false,
		ignoreCompilerErrors: true,
	})
]
```

You can pass either absolute or relative paths as the configuration parameter out. The default output path of the docs is relative to the output path specified in the webpack configuration. For example:

```
output: {
	path: './target/',
}
```

With the default configuration, the above example would produce the docs under the following path: ./target/docs.

Relative paths can also be specified as the out parameter. For example out: '../docs', would produce the docs under the following path: ./docs.
