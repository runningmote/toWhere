<template>
  <div ref="wrapper">
    <div class="header">
      <div class="header-left">
        <div class="iconfont back-icon">&#xe624;</div>
      </div>
      <div class="header-input">
        <span class="iconfont size-icon">&#xe613;</span>
        输入城市/景点/游玩主题
      </div>
      <router-link to="/city">
        <div class="header-right">
          {{this.city}}
          <span class="iconfont arrow-icon">&#xeb6d;</span>
        </div>
      </router-link>
    </div>
  </div>
</template>
<script>
import Bscroll from "better-scroll";
import { mapState } from "vuex";
export default {
  name: "HomeHeader",
  computed: {
    ...mapState(["city"])
  },
  mounted() {
    this.scroll = new Bscroll(this.$refs.wrapper);
  }
};
</script>

<style lang="stylus" scoped>
.header {
  display: flex;
  line-height: 0.86rem;
  background: #00bcd4;
  color: #fff;
  z-index: 111;

  .header-left {
    width: 0.64rem;
    padding: 0.01rem 0.08rem 0.01rem 0.07rem;
    float: left;

    .back-icon {
      font-size: 0.26rem;
      font-weight: bolder;
      text-align: center;
    }
  }

  .header-input {
    flex: 1;
    height: 0.6rem;
    line-height: 0.6rem;
    margin-left: 0.1rem;
    margin: 0.13rem 0;
    padding-left: 0.1rem;
    background: #ffffff;
    border-radius: 0.075rem;
    color: rgb(223, 219, 219);

    .size-icon {
      font-size: 0.29rem;
      margin: 0 0.08rem;
    }
  }

  .header-right {
    min-width: 1.12rem;
    padding: 0.01rem 0.1rem;
    float: right;
    text-align: center;
    color: #fff;

    .arrow-icon {
      font-size: 0.001rem;
    }
  }
}
</style>