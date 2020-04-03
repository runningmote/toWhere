<template>
  <div class="icons">
    <swiper :options="swiperOption" v-if="shouIcon">
      <swiper-slide v-for="(page,index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl" alt />
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>
<script>
export default {
  name: "HomeIcons",
  props: {
    list: Array
  },
  data() {
    return {
      swiperOption: {
        pagination: ".swiper-pagination",
        loop: false
      }
    };
  },
  computed: {
    shouIcon() {
      return this.list.length;
    },
    pages() {
      const pages = [];
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8);
        if (!pages[page]) {
          pages[page] = [];
        }
        pages[page].push(item);
      });
      return pages;
    }
  }
};
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl';
@import '~styles/mixins.styl';

.icons >>> .swiper-container {
  height: 0;
  padding-top: 0.2rem;
  height: 3.6rem;
}

.icons >>> .swiper-pagination-bullet {
  width: 6px;
  height: 6px;
  margin: 0 3px 0 5px;
  border-radius: 50%;
  background: rgba(0, 175, 190, 0.8);
}

.swiper-pagination {
  bottom: 6px;
  margin-left: 5px;
}

.icon {
  position: relative;
  float: left;
  width: 25%;
  height: 1.6rem;

  .icon-img {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 31.3%;
    border-sizing: border-box;

    .icon-img-content {
      display: block;
      margin: 0 auto;
      height: 100%;
    }
  }

  .icon-desc {
    position: absolute;
    left: 0.1rem;
    right: 0.1rem;
    bottom: 0;
    height: 0.6rem;
    line-height: 0.7rem;
    text-align: center;
    color: $darkTextColor;
    ellipsis();
  }
}
</style>