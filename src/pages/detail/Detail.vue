<template>
  <div>
    <detail-banner></detail-banner>
    <detail-header></detail-header>
    <detail-list :ticket="list"></detail-list>
    <div class="content"></div>
  </div>
</template>
<script>
import DetailBanner from "./components/Banner";
import DetailHeader from "./components/Header";
import DetailList from "./components/List";
export default {
  name: "Detail",
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  data() {
    return {
      list: [
        {
          title: "促销票",
          children: [
            {
              title: "成人三馆联票",
              children: [
                {
                  title: "成人三馆联票 -某一连锁店销售"
                }
              ]
            },
            {
              title: "成人五馆联票"
            }
          ]
        },
        {
          title: "当日票"
        },
        {
          title: "门票"
        },
        {
          title: "导游服务"
        }
      ]
    };
  }
};
</script>
<style lang="stylus" scoped>
.content {
  height: 50rem;
}
</style>