---
title: 开启 Nodejs 之旅
---

来学习一下 Nodejs ，不然后面用 ES6 的话连编译都成问题。

### 进入 Nodejs 的世界

在 [Nodejs 官网](https://nodejs.org/) 上可以看到，Nodejs 是

> 一个可以安装到本地机器上的 Javascript 运行环境

其实，传统上 Javascript 只能运行在浏览器里，也就是说 Javascript 唯一的运行环境就是浏览器。但是 Nodejs 出现以后，就可以在本地机器上执行 Javascript 了。这个特点带来了 Web 开发的革命。

来解释一下。比如，我们有一个 main.js 文件，里面写一个

```
console.log('hello world');
```

那么在几年前，想要执行这个 main.js 唯一的方法就是把它放到浏览器里执行。

但是，现在，我们本地安装好 nodejs 之后，就可以这样来执行 main.js 了：

```
node main.js
```

其实，nodejs 就是一个剥了皮的 Chrome 浏览器。


### Nodejs 诞生的巨大意义

一个 web 项目，都有前台代码和后台组成，前台代码都是用 html+css+js 来写的，但是传统上由于本地机器不能运行 JS ，所以后台代码是不能用 JS 来写的，于是我们还要学另外一种语言才能写 Web 程序，通常用来写 Web 后台程序的语言有：PHP , Java ，C# ，Python ，Ruby ，Go ...

所以 Nodejs 的意义就在于，现在开发者终于只用学一种语言，就可以同时进行前台和后台的开发了。
