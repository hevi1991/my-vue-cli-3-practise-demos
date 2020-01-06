# 此项目主要用于了解 `vue cli 3` 所带来的功能

## 常用命令

[X] vue create
[X] vue ui
[X] vue serve
[X] vue build 
[X] plugin and preset
[X] vue-cli-service serve
[X] vue-cli-service build (如果不考虑兼容性，可以传入 --modern 减少编译后的项目体积)
[X] vue-cli-service inspect

## 配置项

### 浏览器兼容性

通过 `package.json` 中 `browserslist` 字段或项目根目录下单独一个 `.browserslistrc` 文件进行配置，[具体配置参数参考](https://github.com/browserslist/browserslist)。

### Polyfill

vue-cli默认构建的项目中，`babel` 为 `useBuiltIns: 'usage'`，如果需要特殊调整，[前往参考](https://cli.vuejs.org/zh/guide/browser-compatibility.html#polyfill)

### 关于 public 文件夹

任何放置在 public 文件夹的静态资源都会被简单的复制，而不经过 webpack。你需要通过绝对路径来引用它们。

**何时使用 public 文件夹**

- 你需要在构建输出中指定一个文件的名字。
- 你有上千个图片，需要动态引用它们的路径。
- 有些库可能和 webpack 不兼容，这时你除了将其用一个独立的 <script> 标签引入没有别的选择。

### CSS 相关

[官方文档](https://cli.vuejs.org/zh/guide/css.html#css-%E7%9B%B8%E5%85%B3)

你可以在创建项目的时候选择预处理器 (Sass/Less/Stylus)。如果当时没有选好，内置的 webpack 仍然会被预配置为可以完成所有的处理。你也可以手动安装相应的 webpack loader：

```
# Sass
npm install -D sass-loader node-sass

# Less
npm install -D less-loader less

# Stylus
npm install -D stylus-loader stylus
```

### Webpack 相关

查看 configure-webpack-in-vue-cli-3 的 demo

### 环境变量和模式

你可以替换你的项目根目录中的下列文件来指定环境变量：

```
.env                # 在所有的环境中被载入
.env.local          # 在所有的环境中被载入，但会被 git 忽略
.env.[mode]         # 只在指定的模式中被载入
.env.[mode].local   # 只在指定的模式中被载入，但会被 git 忽略
```

一个环境文件只包含环境变量的“键=值”对：
```
FOO=bar
VUE_APP_SECRET=secret
```
被载入的变量将会对 vue-cli-service 的所有命令、插件和依赖可用。

> 环境加载属性
> 为一个特定模式准备的环境文件的 (例如 .env.production) 将会比一般的环境文件 (例如 .env) 拥有更高的优先级。
> 此外，Vue CLI 启动时已经存在的环境变量拥有最高优先级，并不会被 .env 文件覆写。