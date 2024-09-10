<template>
  <div>
    <h2>Day 01 - 버튼 컴포넌트 만들어보기 <br> <sub>props [부모 -> 자식 값 전달]</sub></h2>
    <JiTest
      :msg="'TextButton'"
      :subMsg="'Sub Title'"
     />
    <BtnEj 
      :btn_tit="btn_tit" 
      :btn_p="btn_p"
    />
    <!-- html바인딩 -->
    <!-- <BtnEj :btn_txt_wrap="btn_txt_wrap"/> -->

    <!-- component응용 -->
    <!-- <div class="btn_flex_wrap">
      <BtnEj
      class="btn btn_01"
      :btn_tit="btn_tit01" 
      :btn_p="btn_p01"
      />
      <BtnEj
      class="btn btn_02"
      :btn_tit="btn_tit02" 
      :btn_p="btn_p02"
      />
      <BtnEj
      class="btn btn_03"
      :btn_tit="btn_tit03" 
      :btn_p="btn_p03"
      />
      <BtnEj
      class="btn btn_04"
      :btn_tit="btn_tit04" 
      :btn_p="btn_p04"
      />
    </div> -->
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

      //component 활용
      // btn_tit01: 'Text01',
      // btn_p01: 'Secondary 01',
      // btn_tit02: 'Text02',
      // btn_p02: 'Secondary 02',
      // btn_tit03: 'Text03',
      // btn_p03: 'Secondary 03',
      // btn_tit04: 'Text04',
      // btn_p04: 'Secondary 04',

      // html로 바인딩
      // btn_txt_wrap: '<h3 style="color:#f9eef1;text-align:left;">Button text</h3> <p style="color:#cec4c7;">Secondary label</p>'
      //html 바인딩하니 메인 scss 먼저 먹힘
    }
  },
}
</script>

<style lang="scss">
  // 컴포넌트 scss 수정 시 scope 빼야 적용
  .btn_flex_wrap {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;

    .btn {
      &_01 {
        .Text_btn{
          background:none;
          box-shadow: 5px 5px 3px rgb(250, 128, 114, 0.2);
          border: 1px solid salmon;
          .ic {background: salmon;}
          .btn_txt_wrap {
            h3{color:#333;}
            p{color:#666;}
          }
        }
      }
      &_02 {
        .ic {background: honeydew;}
      }
      &_03 {
        .Text_btn{
          background:none;
          box-shadow: 5px 5px 3px rgb(250, 128, 114, 0.1);
          border: 1px solid peachpuff;
          color: #444;
          .ic {background: peachpuff;}
          .btn_txt_wrap {
            h3{color:#333;}
            p{color:#666;}
          }
        }
      }
      &_04 {
        .ic {background: khaki;}
      }
    }
  }
</style>
