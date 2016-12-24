# Components

If you want to expand in dashboard, you can create new component.

## Chartjs

#### Register Component

To use the chartjs component, you can register the `Chartjs.vue` component. 

_For example:_

You can register a global component in `app.js`:

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

> Notice: you must compile once if you change the `resource/assets` files.

#### Usage

You can refer to [Chartjs.vue](https://github.com/vue-bulma/vue-admin/blob/master/client/views/charts/Chartjs.vue)

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