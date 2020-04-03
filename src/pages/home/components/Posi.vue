<template>
  <div>
    <div class="item">
      <div class="item-left posi">
        <a class="iconfont back-icon">
          <span class="iconfont arrow-icon text-icon">&#xe61b;</span>定位失败
        </a>
      </div>
      <div class="item-right posi">
        <a class="iconfont back-icon">
          <span class="iconfont arrow-icon">&#xe7fc;</span>必游榜单
        </a>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "HomePosi"
};
</script>
<style lang="stylus" scoped>
.item {
  overflow: hidden;
  border-top: 1px solid #eee;
  border-bottom: 10px solid #eee;

  .posi {
    width: 50%;
    text-align: center;
    height: 0.95rem;
    line-height: 0.9rem;
    box-sizing: border-box;

    .back-icon {
      display: inline-block;
      font-size: 0.28rem;
      color: #000;

      .arrow-icon {
        font-size: 0.32rem;
        margin-right: 0.035rem;
      }

      .text-icon {
        margin-left: 0.025rem;
      }
    }
  }

  .item-left {
    float: left;
    border-right: 1px solid #eee;
  }

  .item-right {
    float: right;
  }

  .posi:after {
    content: '';
    display: block;
    height: 0;
    visibility: hidden;
    clear: both;
  }
}
</style>