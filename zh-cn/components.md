# 组件

如果你想扩展一下后台面板，你可以创建新的组件。

## Chartjs

你可以使用 `Chartjs` 组件, 只需要注册 `Chartjs.vue` 文件即可。

_例如:_

你可以在 `app.js` 中注册一个全局组件, 提供给后台任何一个页面使用。

```javascript
Vue.component(
    'chart',
    require('./components/Chartjs.vue')
);
```
Of course, you can also register for the page:

```javascript
import Chart from './components/Chartjs.vue'

export default {
    component: {
        Chart
    }
}

```

> 注意：如果你改变了 `resource/assets` 下的文件，你必须重新编译一次。