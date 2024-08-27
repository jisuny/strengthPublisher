<template>
  <div>
    <HelloWorld/>
    <hr />
    <lifeCycle/>
    <hr />
    <VBind/>
    <hr />
    <VPropsEmit/>
  </div>
</template>

<script>
import HelloWorld from './pages/main01/HelloWorld.vue'
import lifeCycle from './pages/main02/lifeCycle.vue'
import VBind from './pages/main03/VBind.vue'
import VPropsEmit from './pages/main04/VPropsEmit.vue'


export default {
  name: 'App',
  components: {
    HelloWorld,
    lifeCycle,
    VBind,
    VPropsEmit
  }
}
</script>

<style>
@import './assets/scss/_reset.scss';
@import './assets/scss/_common.scss';

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
