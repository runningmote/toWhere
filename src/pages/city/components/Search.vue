<template>
  <div>
    <div class="search">
      <input v-model="keyword" class="search-input" type="text" placeholder="输入城市名或拼音" />
    </div>
    <div class="item-list wrapper" ref="wrapper" v-show="keyword">
      <ul>
        <li
          class="item-list-content"
          v-for="item of list"
          :key="item.id"
          @click="changeCityClick(item.name)"
        >{{item.name}}</li>
        <li class="item-list-content" v-show="hasNoData">没有找到相关匹配</li>
      </ul>
    </div>
  </div>
</template>
<script>
import Bscroll from "better-scroll";
import { mapMutations } from "vuex";
export default {
  name: "CitySearch",
  props: {
    cities: Object
  },
  data() {
    return {
      keyword: "",
      list: [],
      timer: null
    };
  },

  computed: {
    hasNoData() {
      return !this.list.length;
    }
  },
  watch: {
    keyword() {
      if (this.timer) {
        clearTimeout(this.timer);
      }
      if (!this.keyword) {
        this.list = [];
        return;
      }
      this.timer = setTimeout(() => {
        const result = [];
        for (let i in this.cities) {
          this.cities[i].forEach(value => {
            if (
              value.spell.indexOf(this.keyword) > -1 ||
              value.name.indexOf(this.keyword) > -1
            ) {
              result.push(value);
            }
          });
        }
        this.list = result;
      }, 300);
    }
  },
  methods: {
    changeCityClick(city) {
      this.changeCity(city);
      this.$router.push("/");
    },
    ...mapMutations(["changeCity"])
  },
  mounted() {
    this.scroll = new Bscroll(this.$refs.wrapper);
  }
};
</script>
<style lang="stylus" scoped>
@import '~styles/varibles.styl';

.search {
  position: absolute;
  top: 0.8rem;
  left: 0;
  right: 0;
  bottom: 0;
  width: 100%;
  height: 0.62rem;
  padding: 0 0.1rem;
  box-sizing: border-box;
  background: $bgColor;
  overflow: hidden;
  z-index: 100;

  .search-input {
    width: 100%;
    box-sizing: border-box;
    height: 0.5rem;
    line-height: 0.5rem;
    padding: 0 0.2rem;
    border-radius: 0.06rem;
    text-align: center;
    background: #fff;
  }
}

.item-list {
  position: absolute;
  width: 100%;
  top: 1.4rem;
  z-index: 1;

  .item-list-content {
    height: 0.8rem;
    line-height: 0.8rem;
    padding-left: 0.2rem;
    background: #fff;
    font-size: 0.32rem;
    border-bottom: 0.02rem solid #ccc;
    color: #000;
    bordere-color: red;
  }
}

.wrapper {
  position: absolute;
  top: 1.4rem;
  left: 0;
  right: 0;
  bottom: 0;
}
</style>