---
title: 目录结构
description: 默认的Nuxt.js应用目录结构意图提供大项目小项目通用的起点。
---

> 默认的Nuxt.js应用目录结构意图提供大项目小项目通用的起点。当然，用户可以按自己意愿随意组织应用。

## 目录

### Assets 资源目录

`assets` 目录包括未编译的文件，如，LESS, SASS, or JavaScript.

[更多文档关于 Assets 整合](/guide/assets)

### Components 组件目录

`components` 目录包含 Vue.js 组件. Nuxt.js doesn't supercharge the data method on these components. //TODO

### Layouts 布局目录

`layouts` 目录包含引用布局。

_这个文件夹不能改名字。_

[更多文档关于 Layouts 整合](/guide/layouts)

### Middleware 中间件目录

_Coming soon_

### Pages 页面目录

`pages` 目录包含引用的视图和路由。框架读取目录中所有 `.vue` 文件，并按照目录结构创建路由。

_这个文件夹不能改名字。_

[更多文档关于 页面 integration](/guide/pages)

### Plugins 插件目录

`plugins` 目录包含Javascript插件，实例化vuejs root对象之前运行这些插件。

[更多文档关于 插件 integration](/guide/plugins)

### Static 静态文件目录

`static` 目录包含所有静态资源文件。目录下每一个文件都被映射到地址 /.

**例子:** /static/robots.txt 映射为 /robots.txt

_这个文件夹不能改名字。_

[更多文档关于 Static integration](/guide/static)

### Store Vuex目录

`store` 目录包含 [Vuex Store](http://vuex.vuejs.org) 文件. Vuex Store 启用选项内置到了 Nuxt.js 框架中. 该目录下创建 `index.js` 文件将自动激活框架的Vuex Store功能。

_这个文件夹不能改名字。_

[更多文档关于 Store integration](/guide/vuex-store)

### nuxt.config.js 文件

`nuxt.config.js` 文件包含 Nuxt.js 自定义配置信息。

_这个文件不能改名字。_

[更多文档关于 nuxt.config.js integration](/guide/configuration)

### package.json 文件

`package.json` 文件包含应用的依赖和Scripts.

_这个文件不能改名字。_

## Aliases 别名/缩写

| Alias | 目录 |
|-----|------|
| ~ | / |
| ~assets | /assets |
| ~components | /components |
| ~pages | /pages |
| ~plugins | /plugins |
| ~static | /static |
| ~store | /store |
