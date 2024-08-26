<template>
  <div>
    <HelloWorld/>
    <hr />
    <lifeCycle/>
    <hr />
    <VBind/>
  </div>
</template>

<script>
import HelloWorld from './pages/main01/HelloWorld.vue'
import lifeCycle from './pages/main02/lifeCycle.vue'
import VBind from './pages/main03/VBind.vue'


export default {
  name: 'App',
  components: {
    HelloWorld,
    lifeCycle,
    VBind
  }
}
</script>

<style lang="scss">
@import './assets/scss/_reset.scss';

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  hr{
    margin:30px 0;
  }
  h2{
    margin-bottom:20px;
    color:#464646;
  }
}
</style>
