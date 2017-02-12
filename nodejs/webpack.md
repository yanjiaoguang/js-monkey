---
title: 如何用 Webpack + Babel 来编译 ES6 ?
---

[nemwing文档](http://newming.coding.me/myidoc)

使用 Babel 的在线编译环境，实际项目中没有办法使用，因为比较麻烦。实际中，我们是试用命令行工具，来自动化的完成编辑工作的。具体涉及到工具就是 Webpack 和 Babel 。

Webpack 是一个 bundler (把多个 js 模块打包成一个文件)，但是同时 Webpack 也是目前最常用的
一个 **预处理** 工具，可以配合多种工具（或者理解为插件）来使用，而 Babel 只是其中一种。

当代职业开发者，手写的代码基本上都是浏览器不支持的，例如

- SASS ---> css
- HAML/JSX ---> html
- ES6 ---> ES5 JS

但是，只需要进行一下 **预处理**（ES6 编译 ES5 ，进行 JS 代码的压缩，文件合并，Sass 转 CSS ...）
就可以真正运行了。而 Webpack 就是这样一个预处理工具。用不用预处理步骤，是区分业余开发者和职业开发者
的一个明显特征。


### node 项目

- 初始化 node 项目 `npm init`, 生成 `package.json`
- 安装 webpack，babel 模块

```
npm install webpack --save-dev||-D
npm install --save-dev babel-loader babel-core
```

webpack 使用时，需要增加它的配置文件，在配置文件里，记录 webpack 各项配置，它的配置文件默认 `webpack.config.js`

```js
var path = require('path');

module.exports = {
    entry: path.resolve(__dirname, 'index.js'),
    output: {
        // path: path.resolve(__dirname, 'build'),
        filename: 'bundle.js'
    },
    module: {
      loaders: [
        {
          test: /\.js$/,
          exclude: /node_modules/,
          loader: "babel-loader"
        }
      ]
    }
};

```

上面的配置文件中，有三大要素需要知道，具体语法可以不用死记：

- 输入文件 index.js ，里面是我们手写的 ES6 代码
- 输出文件 bundle.js ，里面的代码浏览器是可以原生支持的
- 指定的编译器 babel ，babel 使用方式是作为一个 webpack 的 loader


package.json scripts 字段，定义我们的命令

```js
"build": "./node_modules/.bin/webpack -w"
```

配置 babel-loader,添加 .babelrc 文件

```
npm install --save-dev babel-preset-latest
```


```js
{
  "presets": ["latest"]
}
```
