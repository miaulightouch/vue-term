# vue-term3

xtermjs + Vue.js, fork from [vue-term], but build with vue-cli 3.

## Installation

Yarn:

```bash
$ yarn add vue-term3
```

For developer

```bash
$ git clone https://github.com/miaulightouch/vue-term
$ cd vue-term
$ yarn
$ yarn build
```

## How to use

```javascript
import Vue
import VueTerm3 from 'vue-term3'

Vue.component('vue-term', VueTerm3)

new Vue({ template: '<vue-term></vue-term>' }).$mount('#app')
```

```html
<!-- insert Vuejs before this -->
<script src="https://unpkg.com/vue-term3/dist/VueTerm3.umd.js"></script>

<div id="app">
  <vue-term ref="term"></vue-term>
</div>

<script>
  Vue.component('vue-term', VueTerm3)
  var app = new Vue()
  app.$mount('#app')
  app.$refs.term.$stream.pipe(app.$refs.term.$stream)
</script>
```

### Properties

See [Terminal.ts][properties] in xterm.js

[properties]: https://github.com/xtermjs/xterm.js/blob/master/src/Terminal.ts#L65

`buffer` synchronized property is used to keep buffer between destruction and re-creation of component.

`cols` and `rows` also synchronized property.

### Events

`update-title` is emitted when title is changed.

`blur` and `focus` event are emitted when corresponding event is occurred.

`link` event is emitted when linkified hypertext link is clicked. There's no default action for this event.

### Methods

`fit()` method fits the terminal to parent node.
