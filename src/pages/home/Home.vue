<template>
  <div>
    <home-header></home-header>
    <home-swiper :list="swiperList"></home-swiper>
    <home-icons :list="iconList"></home-icons>
    <home-posi></home-posi>
    <home-hot></home-hot>
    <home-recommend :list="recommendList"></home-recommend>
    <home-weekend :list="weekendList"></home-weekend>
  </div>
</template>

<script>
import axios from "axios";
import HomeHeader from "./components/Header";
import HomeSwiper from "./components/Swiper";
import HomeIcons from "./components/Icons";
import HomeHot from "./components/Hot";
import HomePosi from "./components/Posi";
import HomeRecommend from "./components/Recommend";
import HomeWeekend from "./components/Weekend";
import { mapState } from "vuex";
export default {
  name: "Home",
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomePosi,
    HomeRecommend,
    HomeWeekend,
    HomeHot
  },
  data() {
    return {
      lastCity: "",
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: []
    };
  },
  computed: {
    ...mapState(["city"])
  },
  methods: {
    getHomeInfo() {

    this.getHomeInfoSucc(this.city)

      // axios.get("/api/index.json?city=" + this.city).then(this.getHomeInfoSucc);
    },
    getHomeInfoSucc(res) {
//      res = res.data;
        const indexData = require('../../assets/index.json');
        const vdata = indexData.data;
        var data = {};
        if (indexData.ret && vdata) {
        var flag = false;
        for(var i = 0; i < vdata.length; i++){
          if(vdata[i].city == res){
            data = vdata[i];
            flag = true;
            break;
          }          
        }
        if(!flag){
          data = vdata[0];
        }
        this.swiperList = data.swiperList;
        this.iconList = data.iconList;
        this.recommendList = data.recommendList;
        this.weekendList = data.weekendList;
      }
    }
  },
  mounted() {
    this.lastCity = this.city;
    this.getHomeInfo();
  },
  activated() {
    if (this.lastCity !== this.city) {
      this.lastCity = this.city;
      this.getHomeInfo();
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
