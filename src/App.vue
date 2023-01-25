<template>
  <v-main-wrapper />
</template>


<script>
import vMainWrapper from './components/v_main_wrapper.vue';
export default {
  name: 'App',
  components: {
    vMainWrapper
  }
}
</script>

<style lang="scss" scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin-top: 60px;
}
</style>