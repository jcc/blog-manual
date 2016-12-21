# Components

If you want to expand in dashboard, you can create new component.

## Chartjs

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