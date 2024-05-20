<template>
  <button @click="this.show = true">Click Me</button>
  <QuickToastify
    :isShow="show"
    :close="close"
  />
</template>

<script>
import QuickToastify from './components/QuickToastify.vue';

export default {
  name: 'App',
  components: {
    QuickToastify
  },
  data(){
    return{
      show: false
    }
  },
  methods:{
    close(){
      this.show = false;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
