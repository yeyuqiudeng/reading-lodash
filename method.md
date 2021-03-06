# lodash源码分析之method

本文为读 lodash 源码的第三百五十六篇，后续文章会更新到这个仓库中，欢迎 star：[pocket-lodash](https://github.com/yeyuqiudeng/pocket-lodash)

gitbook也会同步仓库的更新，gitbook地址：[pocket-lodash](https://www.gitbook.com/book/yeyuqiudeng/pocket-lodash/details)

## 依赖

```javascript
import invoke from './invoke.js'
```

[《lodash源码分析之invoke》](./invoke.md)


## 源码分析

`method` 是 `invoke` 的偏函数。接收路径 `path` 和参数 `args` ，返回一个函数，这个函数接收一个 `object` 作为参数，这个函数被调用时，会调用 `object` 对应路径 `path` 上的方法，并且将 `args` 作为方法的参数传入。

源码如下：

```javascript
function method(path, args) {
  return (object) => invoke(object, path, args)
}
```

其实返回的函数就是调用 `invoke` 方法。

## License 

[署名-非商业性使用-禁止演绎 4.0 国际 (CC BY-NC-ND 4.0)](http://creativecommons.org/licenses/by-nc-nd/4.0/)

最后，所有文章都会同步发送到微信公众号上，欢迎关注,欢迎提意见：  ![](https://raw.githubusercontent.com/yeyuqiudeng/resource/master/images/qrcode_front-end-article.jpg) 

作者：对角另一面 

