# 在 vue-cli 3 下配置 webpack

## 简单的配置方式

调整 webpack 配置最简单的方式就是在 vue.config.js 中的 configureWebpack 选项提供一个对象，该对象将会被 webpack-merge 合并入最终的 webpack 配置。

```
// vue.config.js
module.exports = {
  configureWebpack: {
    plugins: [
      new MyAwesomeWebpackPlugin()
    ]
  }
}
```
如果你需要基于环境有条件地配置行为，或者想要直接修改配置，那就换成一个函数 (该函数会在环境变量被设置之后懒执行)。该方法的第一个参数会收到已经解析好的配置。在函数内，你可以`直接修改配置`或者`返回一个将会被合并的对象`：

> 直接修改配置，不会被合并，需要考虑清楚，建议返回一个对象进行合并

```
// vue.config.js
module.exports = {
  configureWebpack: config => {
    if (process.env.NODE_ENV === 'production') {
      // 为生产环境修改配置...
    } else {
      // 为开发环境修改配置...
    }
  }
}
```

## [链式操作](https://cli.vuejs.org/zh/guide/webpack.html#%E9%93%BE%E5%BC%8F%E6%93%8D%E4%BD%9C-%E9%AB%98%E7%BA%A7)

除了上面那种方式修改webpack配置外，vue-cli 还支持基于 [webpack-chain](https://github.com/neutrinojs/webpack-chain) 的链式调用来修改。

当你打算链式访问特定的 loader 时，`vue inspect` 会[非常有帮助](https://cli.vuejs.org/zh/guide/webpack.html#%E5%AE%A1%E6%9F%A5%E9%A1%B9%E7%9B%AE%E7%9A%84-webpack-%E9%85%8D%E7%BD%AE)。

举例：修改 Loader 选项
```
// vue.config.js
module.exports = {
  chainWebpack: config => {
    config.module
      .rule('vue')
      .use('vue-loader')
        .loader('vue-loader')
        .tap(options => {
          // 修改它的选项...
          return options
        })
  }
}
```