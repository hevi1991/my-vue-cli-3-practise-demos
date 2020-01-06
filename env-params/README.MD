# 此项目用于演示如何配置 `.env` 环境变量

只有以 `VUE_APP_` 开头的变量会被 webpack.DefinePlugin 静态嵌入到客户端侧的包中。你可以在应用的代码中这样访问它们。

```
console.log(process.env.VUE_APP_SECRET)
```

去查看 `public/index.html` 和 `src/main.js` 使用环境变量的调用。

> 注意 .env 文件的内容可以被覆盖