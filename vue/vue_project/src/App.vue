<template>
  <div>
    <HelloWorld/>
    <hr />
    <lifeCycle/>
    <hr />
    <VBind/>
    <hr />
    <VPropsEmit/>
    <hr />
    <TodoClone/>
    <a 
    href="https://url.kr/jeteg6" 
    target="_blank" 
    title="새창열림"
    class="link_btn western"
    >
      <span>Global leader in eco-friendly energy</span>
      <p>새로운 시대를 여는 <br>친환경 에너지 글로벌 리더</p>
      <em>WP PTS 바로가기 &gt;</em>
    </a>
  </div>
</template>

<script>
import HelloWorld from './pages/main01/HelloWorld.vue'
import lifeCycle from './pages/main02/lifeCycle.vue'
import VBind from './pages/main03/VBind.vue'
import VPropsEmit from './pages/main04/VPropsEmit.vue'
import TodoClone from './pages/main05/TodoClone.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    lifeCycle,
    VBind,
    VPropsEmit,
    TodoClone,
  }
}
</script>

<style lang="scss">
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
