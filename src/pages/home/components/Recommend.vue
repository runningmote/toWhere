<template>
  <div>
    <div class="title">
      <span class="iconfont icon">&#xe600;</span>
      猜你喜欢
    </div>
    <ul>
      <router-link
        tag="li"
        class="item border-bottom"
        v-for="item of list"
        :key="item.id"
        :to="'/detail/' + item.id"
      >
        <img class="item-img" :src="item.imgUrl" alt />
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </router-link>
    </ul>
  </div>
</template>
<script>
export default {
  name: "HomeRecommend",
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

.item {
  overflow: hidden;
  display: flex;
  height: 1.9rem;

  .item-img {
    width: 1.7rem;
    height: 1.7rem;
    padding: 0.1rem;
  }

  .item-info {
    flex: 1;
    padding: 0.1rem;
    min-width: 0;

    .item-title {
      line-height: 0.54rem;
      font-size: 0.32rem;
      ellipsis();
    }

    .item-desc {
      font-size: 0.24rem;
      margin-top: 0.1rem;
      color: #ff8888;
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
}
</style>