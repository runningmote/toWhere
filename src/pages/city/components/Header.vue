<template>
  <div>
    <div class="item">
      <router-link to="/">
        <span class="iconfont back-icon">&#xe624;</span>
      </router-link>城市选择
    </div>
  </div>
</template>
<script>
export default {
  name: "CityHeader"
};
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.item {
  position: relative;
  overflow: hidden;
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