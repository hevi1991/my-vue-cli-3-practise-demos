# 关于插件和Preset

> `Vue Cli` 使用了一套基于插件架构，专为脚手架编写的插件`npm`包，均已 `@vue/cli-plugin-` 开头命名。

## 插件安装

在现有项目中安装插件

```
vue add eslint
```

## Preset 预设

 preset 是一个包含创建新项目所需预定义选项和插件的 JSON 对象，让用户无需在命令提示中选择它们。

 在 `vue create` 过程中保存的 `preset` 会被放在你的 `home` 目录下的一个配置文件中 (`~/.vuerc`)。你可以通过直接编辑这个文件来调整、添加、删除保存好的 `preset`。

 preset 示例：
 
 ```
 {
  "useConfigFiles": true,
  "cssPreprocessor": "sass",
  "plugins": {
    "@vue/cli-plugin-babel": {},
    "@vue/cli-plugin-eslint": {
      "config": "airbnb",
      "lintOn": ["save", "commit"]
    },
    "@vue/cli-plugin-router": {},
    "@vue/cli-plugin-vuex": {}
  }
}
 ```