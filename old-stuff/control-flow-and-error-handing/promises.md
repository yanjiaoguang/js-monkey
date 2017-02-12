# Promise 对象

从 ECMAScript2015 开始,JavaScript 提供了对 Promise 对象的支持，允许你控制流程的延迟和异步操作。

一个 Promise 对象会处在以下一种状态：

- pending: 默认状态， 不是 fulfilled 或 rejected。
- fulfilled: 已完成
- rejected: 已失败
- settled: fulfilled or rejected 状态，不是 pending。

![promise](http://o8jmxixgd.bkt.clouddn.com/promises.png)

### 通过 XHR 加载一张图片

一个简单的例子使用 Promise 和 XMLHttpRequest 来加载一个在 MDN GitHub [promise-test](https://github.com/mdn/promises-test/blob/gh-pages/index.html) 仓库的图像。也可以 [查看实例](http://mdn.github.io/promises-test/)。每一步都有注释，允许你遵守 Promise 和 XHR 架构。下面是未注释版本,显示  Promise 流,这样你就可以得到一个整体想法:

```
function imgLoad(url) {
  return new Promise(function(resolve, reject) {
    var request = new XMLHttpRequest();
    request.open('GET', url);
    request.responseType = 'blob';
    request.onload = function() {
      if (request.status === 200) {
        resolve(request.response);
      } else {
        reject(Error('Image didn\'t load successfully; error code:'
                     + request.statusText));
      }
    };
    request.onerror = function() {
      reject(Error('There was a network error.'));
    };
    request.send();
  });
}
```
