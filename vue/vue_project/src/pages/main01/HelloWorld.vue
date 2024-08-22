<template>  
  <div>
    <JiTest
      :msg="'TextButton'"
      :subMsg="'Sub Title'"
     />
    <EjTest />
  </div>
</template>

<script>
import JiTest from '../../components/day01/JiseonTxt.vue';
import EjTest from '../../components/day01/Eunji.vue';

export default {
  components: {
    JiTest,
    EjTest
  },
  data(){
    return{

    }
  },
}

</script>

<style lang="scss" scoped>

</style>
