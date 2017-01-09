---
title: Pages 目录
description: pages 目录允许通过简单的创建vue文件树自动生成各种类型路由。这些含有一沓特性的组件可以令起手和维护项目变得简易省心。
---

> `pages` 目录允许通过简单的创建vue文件树自动生成各种类型路由。这些含有一沓特性的组件可以令起手和维护项目变得简易省心。

## Special Keys 特定的key

每一个page组件都是一个Vue组件，但nuxt.js为其添加了特定的key，以最简单的方式实现应用的通用性。

所有的 key

| 属性 | 描述 |
|-----------|-------------|
| data | 最重要的 key, 它和 [Vue data](https://vuejs.org/v2/api/#Options-Data) 目的一致，但可以异步获取，也可以直接接受上下文作为参数。实例在 [async data 文档](/guide/async-data) . |
| fetch | 用来在渲染页面之前填充 store 数据。它跟data method很像，只不过本身不设置组件的data。 实例 [fetch method 文档](/guide/vuex-store#the-fetch-method). |
| layout | 用来指定已在`layouts`文件夹中定义的布局。 实例在 [layouts documentation](/guide/layouts). |
| transition | 为页面设置制定的切换效果。 实例在 [routes transitions](/guide/routes-transitions). |
| scrollToTop | Boolean 布尔值, 默认: `false`. 可设置切换页面的时是否跳转到页面顶端。常用在 [嵌套的路由](/guide/nested-routes). |
| validate | 为 [动态路由](/guide/dynamic-routes#validate-route-params).提供验证功能 |
| middleware | 为页面设置中间件，渲染页面之前会call中间件。实例在 [routes middleware](/guide/routes-middleware). |


## Simple 页面

page组件是预设了一些内容的Vue组件。首先，我们创建一个显示红色‘Hello World！’标题的最简单例子。

我们创建第一个页面 `pages/index.vue`:

```html
<template>
  <h1 class="red">Hello {{ name }}!</h1>
</template>

<script>
export default {
  data () {
    return { name: 'World' }
  }
}
</script>

<style>
.red {
  color: red;
}
</style>
```

## 加上预处理过程

Thanks to [vue-loader](http://vue-loader.vuejs.org/en/configurations/pre-processors.html), 可以为 `<template>`, `<script>` or `<style>` 使用各种预处理器: 通过填上 `lang` 属性即可自动实现.

例子 `pages/index.vue` 使用 [Pug](https://github.com/pugjs/pug), [CoffeeScript](http://coffeescript.org) 和 [Sass](http://sass-lang.com/):

```html
<template lang="pug">
  h1.red Hello {{ name }}!
</template>

<script lang="coffee">
module.exports = data: ->
  { name: 'World' }
</script>

<style lang="sass">
.red
  color: red
</style>
```

使用这些 pre-processors, 需要安装对应的 webpack loaders:
```bash
npm install --save-dev pug@2.0.0-beta6 pug-loader coffee-script coffee-loader node-sass sass-loader
```

## 使用 JSX

想在组件中使用 JSX 的话, 首先，要安装 JSX 的 Babel 插件

```bash
npm install --save-dev babel-plugin-syntax-jsx babel-plugin-transform-vue-jsx babel-helper-vue-jsx-merge-props
```

然后, 在配置文件 `nuxt.config.js` 中, 启用 [transform-vue-jsx](https://github.com/vuejs/babel-plugin-transform-vue-jsx) 插件:

```js
module.exports = {
  build: {
    babel: {
      plugins: ['transform-vue-jsx']
    }
  }
}
```

更多babel 配置项，察看 [build config documentation](/api/configuration-build).

可以在组件中 `render` 方法下使用JSX了:

```html
<script>
export default {
  data () {
    return { name: 'World' }
  },
  render (h) {
    return <h1 class="red">{this.name}</h1>
  }
}
</script>
```

可在Vue文档中 [JSX 部分](https://vuejs.org/v2/guide/render-function.html#JSX) 了解JSX 在nuxt中的使用。
