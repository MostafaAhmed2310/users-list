<template>
  <div id="app">
     <task></task>
  </div>
</template>
<script>
import task from './components/task.vue'

export default {
  name: 'app',
  components: {
    task
  }



}
</script>

<style>
*{
  font-size:7pt;
  font-family:verdana;
  text-align:center;
}
</style>
