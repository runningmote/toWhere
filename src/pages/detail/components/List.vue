<template>
  <div>
    <div class="item" v-for="(item,index) of ticket" :key="index">
      <div class="item-title border-bottom">
        <span class="item-title-icon"></span>
        {{item.title}}
      </div>
      <div v-if="item.children" class="item-chilren">
        <detail-list :ticket="item.children"></detail-list>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "DetailList",
  props: {
    ticket: Array
  }
};
</script>
<style lang="stylus" scoped>
.item-title {
  line-height: 0.8rem;
  padding: 0 0.2rem;
  font-size: 0.32rem;

  .item-title-icon {
    position: relative;
    top: 0.06rem;
    left: 0.06rem;
    display: inline-block;
    width: 0.36rem;
    height: 0.36rem;
    background: url('http://s.qunarzz.com/piao/image/touch/sight/detail.png') 0 -0.45rem no-repeat;
    margin-right: 0.1rem;
    background-size: 0.4rem 3rem;
  }
}

.item-chilren {
  padding: 0 0.2rem;
}
</style>