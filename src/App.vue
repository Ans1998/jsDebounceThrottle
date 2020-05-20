<template>
  <div id="app_content">
    <Debounce />
    <Throttle />
  </div>
</template>

<script>
import Debounce from './components/Debounce'
import Throttle from './components/Throttle'
export default {
  name: 'App',
  components: {Debounce, Throttle},
  data() {
    return {
    }
  },
  mounted() {
  }
}
</script>

<style>

</style>
