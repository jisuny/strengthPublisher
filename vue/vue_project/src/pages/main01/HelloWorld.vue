<template>
  <h2>Day 01 - 버튼 컴포넌트 만들어보기 <br> <sub>props [부모 -> 자식 값 전달]</sub></h2>
  <div>
    <JiTest
      :msg="'TextButton'"
      :subMsg="'Sub Title'"
     />
    <BtnEj :btn_tit="btn_tit" :btn_p="btn_p"/>
    <!-- <BtnEj :btn_txt_wrap="btn_txt_wrap"/> -->
  </div>
</template>

<script>
import JiTest from '../../components/day01/JiseonTxt.vue';
import BtnEj from '../../components/day01/Eunji.vue';

export default {
  components: {
    JiTest,
    BtnEj 
  },
  data(){
    return{
      btn_tit: 'Button text',
      btn_p: 'Secondary label',
      // btn_txt_wrap: '<h3 style="color:#f9eef1;text-align:left;">Button text</h3> <p style="color:#cec4c7;">Secondary label</p>'
      //html 바인딩하니 메인 scss 먼저 먹힘
    }
  },
}

</script>

<style lang="scss" scoped>

</style>
