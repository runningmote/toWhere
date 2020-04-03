<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img
        class="banner-img"
        src="//img1.qunarzz.com/sight/p0/1411/b6/662fc49d1d26a5a7775cf6b7f8b4ecec.water.jpg_600x330_c34588e7.jpg"
        alt
      />
      <div class="banner-info">
        <div class="banner-title">杭州野生动物世界(AAAA景区)</div>
        <div class="banner-number">
          视频
          <span class="iconfont icon">&#xe601;</span>
        </div>
      </div>
    </div>
    <common-gallary :imgs="imgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
  </div>
</template>
<script>
import CommonGallary from "common/gallary/Gallary";
export default {
  name: "DetailBanner",
  data() {
    return {
      showGallary: false,
      imgs: [
        "http://img1.qunarzz.com/sight/p0/1411/b6/662fc49d1d26a5a7775cf6b7f8b4ecec.water.jpg_r_800x800_9991406f.jpg",
        "http://img1.qunarzz.com/sight/p0/1902/32/325daff41d4de016a3.img.jpg_r_800x800_d93d20d0.jpg",
        "http://img1.qunarzz.com/sight/p0/1902/cb/cb713dea76fc85b5a3.img.jpg_r_800x800_164bd654.jpg",
        "http://img1.qunarzz.com/sight/p0/1902/de/deb5ef09cc5fa8a3a3.img.jpg_r_800x800_65f007b9.jpg",
        "http://img1.qunarzz.com/sight/p0/1902/22/220010667ed4b38ba3.img.jpg_r_800x800_fb77c355.jpg",
        "http://img1.qunarzz.com/sight/p0/1902/c8/c8e2f8be64baf833a3.img.jpg_r_800x800_7604f810.jpg",
        "http://img1.qunarzz.com/sight/p0/1902/e9/e9462cd01bd3a9cba3.img.jpg_r_800x800_2994bee8.jpg",
        "http://img1.qunarzz.com/sight/p0/1902/ec/ec4d1d341fb67d1ba3.img.jpg_r_800x800_3d729020.jpg",
        "http://img1.qunarzz.com/sight/p0/1902/f3/f37be645ae6e225fa3.img.jpg_r_800x800_8a525315.jpg",
        "http://img1.qunarzz.com/sight/p0/1902/7e/7ef8d69b0dbbd261a3.img.jpg_r_800x800_ae59daca.jpg",
        "http://img1.qunarzz.com/sight/p0/201405/22/26d6ee391ffa8863aa9da2be1c55beaf.jpg_r_800x800_b84b278d.jpg",
        "http://img1.qunarzz.com/sight/p0/1505/14/14dd5373a91f53a4.water.jpg_r_800x800_ef2667d8.jpg",
        "http://img1.qunarzz.com/sight/p0/201403/07/3e0e72b80bf4818df89716a1a8f7cfee.jpg_r_800x800_f7365e31.jpg",
        "http://img1.qunarzz.com/sight/p0/201405/21/c16d3b8d828acc15fec8352af5d0f2d7.jpg_r_800x800_022f6f0c.jpg"
      ]
    };
  },
  methods: {
    handleBannerClick() {
      this.showGallary = true;
    },
    handleGallaryClose() {
      this.showGallary = false;
    }
  },
  components: {
    CommonGallary
  }
};
</script>
<style lang="stylus" scoped>
.banner {
  position: relative;
  overflow: hidden;
  height: 0;
  padding-bottom: 55%;

  .banner-img {
    width: 100%;
  }

  .banner-info {
    display: flex;
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0.26rem;
    line-height: 0.6rem;
    color: #fff;
    background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.4));

    .banner-title {
      flex: 1;
      font-size: 0.36rem;
      padding: 0 0.2rem;
    }

    .banner-number {
      height: 0.6rem;
      line-height: 0.6rem;
      padding: 0 0.1rem;
      margin-right: 0.06rem;
      font-size: 0.36rem;
      border-radius: 0.2rem;

      .icon {
        font-size: 0.4rem;
      }
    }
  }
}
</style>