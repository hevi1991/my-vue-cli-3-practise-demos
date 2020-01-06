## 注意

要使用 `vue serve` 或 `vue build` 命令对单个 `*.vue` 文件进行快速原型开发，需要额外安装一个全局扩展
```
npm install -g @vue/cli-service-global
```

## 运行

在此路径下，执行以下命令
```
vue serve
```
```
vue build
```

## 用法
```
Usage: serve [options] [entry]

在开发环境模式下零配置为 .js 或 .vue 文件启动一个服务器

Options:

  -o, --open  打开浏览器
  -c, --copy  将本地 URL 复制到剪切板
  -h, --help  输出用法信息
  
```
```
Usage: build [options] [entry]

在生产环境模式下零配置构建一个 .js 或 .vue 文件


Options:

  -t, --target <target>  构建目标 (app | lib | wc | wc-async, 默认值：app)
  -n, --name <name>      库的名字或 Web Components 组件的名字 (默认值：入口文件名)
  -d, --dest <dir>       输出目录 (默认值：dist)
  -h, --help             输出用法信息
```