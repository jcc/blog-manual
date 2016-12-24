# 组件

如果你想扩展一下后台面板，你可以创建新的组件。

## Chartjs

#### 注册组件

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

#### 使用

使用方法可参考 [Chartjs.vue](https://github.com/vue-bulma/vue-admin/blob/master/client/views/charts/Chartjs.vue)

```html
<template>
  <div class="row">
      <div class="ibox">
          <div class="ibox-title">
              <h5 class="no-margins">PIE</h5>
          </div>
          <div class="ibox-content">
              <chart :type="'pie'" :data="pieData" :options="options"></chart>
          </div>
      </div>
  </div>
</template>

<script>
  import Chart from './components/Chartjs.vue'

  export default {
      component: {
          Chart
      },

      data () {
        return {
          labels: ['Sleeping', 'Designing', 'Coding', 'Cycling'],
          data: [20, 40, 5, 35],
          options: {
            segmentShowStroke: false
          },
          backgroundColor: [
            '#1fc8db',
            '#fce473',
            '#42afe3',
            '#ed6c63',
            '#97cd76'
          ],
        }
      },

      computed: {
        pieData () {
          return {
            labels: this.labels,
            datasets: [{
              data: this.data,
              backgroundColor: this.backgroundColor
            }]
          }
        }
      }
  }
</script>
```