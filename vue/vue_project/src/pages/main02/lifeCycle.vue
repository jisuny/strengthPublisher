<template>
  <h2>Day 02 - 라이프 사이클 익히기 <br> <sub>vue3 기준</sub></h2>
  <img src="../../assets/images/day02/vue3_life_sycle.webp" alt="라이프 사이클 이미지">
  <div>
    <JiLife />
    <EjLife />
  </div>
</template>

<script>
import JiLife from '../../components/day02/JiLife.vue';
import EjLife from '../../components/day02/EjLife.vue';

export default {
  components: {
    JiLife,
    EjLife 
  },
  data(){
    return{
    }
  },
}

</script>

<style lang="scss" scoped>
  img{
    margin:0 auto;
    max-width:1080px;
    width:100%;
    
  }
</style>
