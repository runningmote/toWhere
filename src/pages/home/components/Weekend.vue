<template>
  <div>
    <div class="title">周末去哪</div>
    <ul>
      <li class="item border-bottom" v-for="item of list" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" alt />
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: "HomeWeekend",
  props: {
    list: Array
  }
};
</script>
<style lang="stylus" scoped>
@import '~styles/mixins.styl';

.title {
  line-height: 0.8rem;
  background: #ffffff;
  text-indent: 0.2rem;

  .icon {
    margin-left: 0.2rem;
    color: #FF3333;
  }
}

.item-img-wrapper {
  overflow: hidden;
  height: 0;
  padding-bottom: 37.5%;

  .item-img {
    width: 100%;
  }
}

.item-info {
  flex: 1;
  padding: 0.14rem 0.2rem 0.2rem;
  min-width: 0;

  .item-title {
    height: 0.48rem;
    line-height: 0.48rem;
    font-size: 0.28rem;
    ellipsis();
  }

  .item-desc {
    height: 0.42rem;
    line-height: 0.42rem;
    font-size: 0.12rem;
    color: #666;
    ellipsis();
  }

  .item-button {
    line-height: 0.44rem;
    margin-top: 0.16rem;
    background: #ff9300;
    padding: 0.1rem;
    border-radius: 0.06rem;
    color: #fff;
  }
}
</style>