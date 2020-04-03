<template>
  <div>
    <router-link v-show="showAbs" tag="div" to="/" class="header-abs">
      <div class="iconfont back-icon">&#xe624;</div>
    </router-link>
    <div class="item" v-show="!showAbs" :style="opacityStyle">
      <router-link to="/">
        <span class="iconfont back-icon">&#xe624;</span>
      </router-link>查看详情
    </div>
  </div>
</template>
<script>
export default {
  name: "DetailHeader",
  data() {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    };
  },
  methods: {
    handleScroll() {
      const top = document.documentElement.scrollTop;
      if (top > 60) {
        let opacity = top / 140;
        opacity = opacity > 1 ? 1 : opacity;
        this.opacityStyle = { opacity };
        this.showAbs = false;
      } else {
        this.showAbs = true;
      }
    }
  },
  activated() {
    window.addEventListener("scroll", this.handleScroll);
  },
  deactivated() {
    window.removeEventListener("scroll", this.handleScroll);
  }
};
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.header-abs {
  position: absolute;
  left: 0.2rem;
  top: 0.2rem;
  width: 0.8rem;
  height: 0.8rem;
  line-height: 0.8rem;
  text-align: center;
  border-radius: 0.4rem;
  background: rgba(0, 0, 0, 0.8);

  .back-icon {
    color: #fff;
  }
}

.item {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  height: 0.86rem;
  line-height: 0.9rem;
  font-size: 0.32rem;
  color: #fff;
  text-align: center;
  background: $bgColor;
  z-index: 12;
  touch-action: none;

  .back-icon {
    position: absolute;
    top: 0;
    left: 0.28rem;
    bottom: 0;
    font-size: 0.26rem;
    font-weight: bold;
    color: #fff;
  }
}
</style>