<template>
  <div class="container">
    <v-main-wrapper/>
  </div>
</template>

<script>
import vMainWrapper from '@/components/v-main-wrapper.vue';

export default {
  components: {
    vMainWrapper,
  },
  data() {
    
  }
}
</script>

<style>
body {
  background: #d6d6d6;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
