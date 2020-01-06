# CLI 服务 

## vue-cli-service serve 启用开发服务

假如采用了 `preset` 进行构建项目后，`package.json` 中 `script` 的默认命令如下：

```
{
  "scripts": {
    "serve": "vue-cli-service serve",
    "build": "vue-cli-service build"
  }
}
```

可通过如下代码启用服务：

```
npm run serve
# 或
yarn serve
```

### 用法

`vue-cli-service serve` 采用优化后 `webpack-dev-server` 的开发服务器，可以通过修改 `vue.config.js` 中的 `devServer` 字段配置开发服务。

```
用法：vue-cli-service serve [options] [entry]

选项：

  --open    在服务器启动时打开浏览器
  --copy    在服务器启动时将 URL 复制到剪切版
  --mode    指定环境模式 (默认值：development)
  --host    指定 host (默认值：0.0.0.0)
  --port    指定 port (默认值：8080)
  --https   使用 https (默认值：false)
```

## vue-cli-service build 打包编译

`vue-cli-service build` 会在 `dist/` 目录产生一个可用于生产环境的包，带有 JS/CSS/HTML 的压缩，和为更好的缓存而做的自动的 vendor chunk splitting。它的 chunk manifest 会内联在 HTML 里。

### 用法

```
用法：vue-cli-service build [options] [entry|pattern]

选项：

  --mode        指定环境模式 (默认值：production)
  --dest        指定输出目录 (默认值：dist)
  --modern      面向现代浏览器带自动回退地构建应用
  --target      app | lib | wc | wc-async (默认值：app)
  --name        库或 Web Components 模式下的名字 (默认值：package.json 中的 "name" 字段或入口文件名)
  --no-clean    在构建项目之前不清除目标目录
  --report      生成 report.html 以帮助分析包内容
  --report-json 生成 report.json 以帮助分析包内容
  --watch       监听文件变化
```

## vue-cli-service inspect 查看当前项目 webpack 的配置

```
用法：vue-cli-service inspect [options] [...paths]

选项：

  --mode    指定环境模式 (默认值：development)
```

## 有些插件会给当下的 `vue-cli-service` 注入一些额外命令

可以通过 `npx vue-cli-service help` 进行查看