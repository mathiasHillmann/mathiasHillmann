<template>
  <div id="app">
    <Desktop />
    <Taskbar />
  </div>
</template>

<script>
import Desktop from './components/Desktop.vue'
import Taskbar from './components/Taskbar.vue'

export default {
  name: 'App',
  components: {
    Desktop,
    Taskbar,
  }
}
</script>

<style>
#app{
  margin: 0px;
  padding: 0px;
  width: 100%;
  height: 100%;
}
</style>
