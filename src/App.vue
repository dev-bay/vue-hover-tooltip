<template>
  <div id="app">
    
    <popover ref="popover" />

    <a href="https://dev-bay.com" data-popover="This is a popover from Dev-Bay.com!">Link to Dev-Bay.com</a>

    <div class="more">
      <div v-for="(i, k) in q" :key="k">
        <a href="https://dev-bay.com" :data-popover="'This is a new link with popover' + i">New link {{i}}</a>
      </div>
      <button @click="addLinks">Add more links</button>
    </div>

  </div>
</template>

<script>
import Popover from './components/popover.vue'

export default {
  name: 'App',
  components: {
    Popover
  },
  data () {
    return {
      q: 0,
    }
  },
  methods: {
    addLinks () {
      this.q += 10;
    }
  },
  updated () {
    this.$refs.popover.init();
  }
}
</script>

<style>
#app {
  width: 500px;
  margin: 20px auto;
}
.more, button {
  margin-top: 20px;
}
</style>
