<template>
  <div class="item">
    <div class="item-icon">
      <span class="iconfont item-icons">&#xe6d1;</span>本周热门榜单
      <span class="item-content">
        全部榜单
        <span class="item-right">></span>
      </span>
    </div>
    <ul class="item-box">
      <li class="item-box-content" v-for="item of list" :key="item.id">
        <img class="item-img" :src="item.imgUrl" alt />
        <div class="box">
          <p class="item-text">{{item.title}}</p>
          <p class="item-text">
            <span class="marny">{{item.desc}}</span>起
          </p>
        </div>
      </li>
    </ul>
    <div class="col"></div>
  </div>
</template>
<script>
export default {
  name: "HomeHot",
  data() {
    return {
      list: [
        {
          id: "0001",
          imgUrl:
            "http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_250x250_0fc722c0.jpg",
          title: "故宫",
          desc: "¥40"
        },
        {
          id: "0002",
          imgUrl:
            "http://img1.qunarzz.com/sight/p0/1505/f5/f5f45e1a83537bcb.water.jpg_250x250_63e3520a.jpg",
          title: "圆明园",
          desc: "¥25"
        },
        {
          id: "0003",
          imgUrl:
            "http://img1.qunarzz.com/sight/p0/1708/2b/2b3b94de99c0a425a3.img.jpg_250x250_50c99cf3.jpg",
          title: "八达岭长城",
          desc: "¥35"
        },
        {
          id: "0004",
          imgUrl:
            "http://img1.qunarzz.com/sight/p0/1505/d2/d274c92de14c93da.water.jpg_250x250_d852635b.jpg",
          title: "颐和园",
          desc: "¥22.9"
        },
        {
          id: "0005",
          imgUrl:
            "http://img1.qunarzz.com/sight/p0/1711/c2/c2f78ad1e34fe4dea3.img.jpg_250x250_6e1f98c0.jpg",
          title: "怀北国际滑雪场",
          desc: "¥30"
        },
        {
          id: "0006",
          imgUrl:
            "http://img1.qunarzz.com/sight/p0/1511/d2/d2aec2dfc5aa771290.water.jpg_250x250_7b67daa3.jpg",
          title: "南山滑雪场",
          desc: "¥120"
        },
        {
          id: "0007",
          imgUrl:
            "http://img1.qunarzz.com/sight/p0/1602/92/920e47352552c1c990.water.jpg_250x250_ee99c18e.jpg",
          title: "天坛公园",
          desc: "13.5"
        },
        {
          id: "0008",
          imgUrl:
            "http://img1.qunarzz.com/sight/p0/1903/5d/5dcaf453dfd6f5dba3.img.jpg_250x250_ad9c739f.jpg",
          title: "古北水镇",
          desc: "¥298"
        },
        {
          id: "0009",
          imgUrl:
            "http://img1.qunarzz.com/sight/p0/1508/fe/434ee530e21f1c11bad088e8cc8d5e93.water.jpg_250x250_12e8154c.jpg",
          title: "鸟巢",
          desc: "¥50"
        },
        {
          id: "00010",
          imgUrl:
            "http://img1.qunarzz.com/sight/p0/1603/85/85c883189bf7293390.water.jpg_250x250_090a42b6.jpg",
          title: "什刹海",
          desc: "¥5"
        }
      ]
    };
  }
};
</script>
<style lang="stylus" scoped>
.item {
  overflow: hidden;
  height: 0;
  padding-bottom: 4.2rem;

  .item-icon {
    overflow: hidden;
    position: relative;
    line-height: 0.8rem;
    font-size: 0.3rem;

    .item-icons {
      margin: 0 0.04rem 0 0.2rem;
      font-size: 0.24rem;
      color: red;
      vertical-align: top;
    }

    .item-content {
      position: absolute;
      right: 0.2rem;
      font-size: 0.2rem;
      color: #999;

      .item-right {
        font-size: 0.3rem;
      }
    }
  }

  .item-box {
    height: 3.3rem;
    overflow-x: scroll;
    white-space: nowrap;

    .item-box-content {
      display: inline-block;
      overflow: hidden;

      .item-img {
        width: 2rem;
        height: 100%;
        margin: 0 0.1rem;
      }

      .box {
        margin-top: 0.2rem;

        .item-text {
          height: 0.35rem;
          line-height: 0.35rem;
          text-align: center;

          .marny {
            color: orange;
          }
        }
      }
    }
  }

  .col {
    height: 0.2rem;
    background: #eee;
  }
}
</style>