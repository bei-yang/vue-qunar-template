/* 展示模板 */
<template>
  <div class='header'>
    <div class='header-left'>
      <span class='iconfont back-icon'>
        &#xe624;
      </span>
    </div>
    <div class="header-input">
      <span class='iconfont'>&#xe632;</span>
      输入城市/景点/游玩主题
    </div>
    <router-link to='/city'
                 tag='div'
                 class="header-right">
      {{this.city}}
      <span class='iconfont arrow-icon'>&#xe64a;</span>
    </router-link>
  </div>
</template>
<script>
//导入组件
import { mapState, mapGetters } from 'vuex'
export default {
  name: 'HomeHeader',
  props: {
    city: String
  },
  computed: {
    ...mapState(['city']),
    ...mapGetters(['doubleCity'])
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/varibies.styl';

.header {
  line-height: $headerHeight;
  display: flex;
  background: $bgColor;
  color: #fff;

  .header-left {
    width: 0.64rem;
    margin-left: 0.2rem;

    .back-icon {
      text-align: center;
      font-size: 0.4rem;
    }
  }

  .header-input {
    flex: 1;
    background: #fff;
    height: 0.64rem;
    line-height: 0.64rem;
    margin-top: 0.12rem;
    margin-left: 0.2rem;
    padding-left: 0.2rem;
    border-radius: 0.02rem;
    color: #ccc;
  }

  .header-right {
    min-width: 1.04rem;
    text-align: center;
    padding: 0 0.1rem;

    .arrow-icon {
      font-size: 0.2rem;
    }
  }
}
</style>
