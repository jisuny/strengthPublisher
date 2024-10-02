<template>
  <div class="wrapper">
    <WpHeader/>
    <!-- 추후 메뉴에 따른 content -->
    <!-- <router-view/> 09.26 라우터 연결 확인하기! -->
    <WpContent/>
    <WpFooter/>
  </div>
</template>

<script>

import WpHeader from './components/WpHeader.vue'
import WpFooter from './components/WpFooter.vue'
import WpContent from './views/contentM.vue'

export default {
  components: {
    WpHeader,
    WpFooter,
    WpContent,
  },
}
</script>

<style lang="scss">
  @import './assets/scss/_reset.scss';
  @import './assets/scss/_common.scss';
  @import './assets/scss/header.scss';
  @import './assets/scss/footer.scss';

  @import './assets/scss/contentM.scss';
</style>
