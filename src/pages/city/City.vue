<template>
  <div>
    <city-header></city-header>
    <city-search :cities="cities"></city-search>
    <city-list :citi="cities" :list="hotCities"></city-list>
  </div>
</template>
<script>
import axios from "axios";
import CityHeader from "./components/Header";
import CitySearch from "./components/Search";
import CityList from "./components/List";
export default {
  name: "City",
  data() {
    return {
      cities: {},
      hotCities: []
    };
  },
  components: {
    CityHeader,
    CitySearch,
    CityList
  },
  mounted() {
        this.getCityInfo();
    //axios.get("/api/city.json").then(this.handleGetCityInfoSucc);
  },
  methods: {
    getCityInfo() {
    const res = require('../../assets/city.json');//加载本地数据文件
      if (res.ret && res.data) {
        const data = res.data;
        this.cities = data.cities;
        this.hotCities = data.hotCities;
      }
    }
  }
};
</script>
<style lang="stylus" scoped></style>