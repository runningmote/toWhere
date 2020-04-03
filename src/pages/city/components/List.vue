<template>
  <div ref="wrapper" class="wrapper">
    <div>
      <div class="item">
        <div class="item-hot col">热门城市</div>
        <div class="item-cities">
          <ul class="item-list" v-for="item of list" :key="item.id">
            <li class="item-cities-content" @click="handleCityClick(item.name)">{{item.name}}</li>
          </ul>
        </div>

        <div class="sort">
          <div class="item-sort col">字母排序</div>
          <div class="item-sort-list">
            <ul class="sort-list" v-for="(item,key) of citi" :key="key" @click="changeSort(key)">
              <li class="sort-list-content">{{key}}</li>
            </ul>
          </div>
        </div>

        <div class="letter" :ref="key" v-for="(item,key) of citi" :key="key">
          <div class="item-letter col">{{key}}</div>
          <div class="letter-list">
            <ul class="item-letter-list">
              <li
                class="item-letter-content border-bottom"
                v-for="innerItem of item"
                :key="innerItem.id"
                @click="handleCityClick(innerItem.name)"
              >{{innerItem.name}}</li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import Bscroll from "better-scroll";
import { mapMutations } from "vuex";
export default {
  name: "CityList",
  props: {
    list: Array,
    citi: Object
  },
  data() {
    return {
      scroll: ""
    };
  },
  mounted() {
    this.scroll = new Bscroll(this.$refs.wrapper);
  },
  methods: {
    changeSort(sortName) {
      this.scroll.scrollToElement(this.$refs[sortName][0]);
    },
    handleCityClick(city) {
      this.$store.commit("changeCity", city);
      this.$router.push("/");
    },
    ...mapMutations(["changeCity"])
  }
};
</script>
<style lang="stylus" scoped>
.border-bottom {
  &:before {
    border-color: #ccc;
  }

  &:after {
    border-color: #ccc;
  }
}

.wrapper {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  top: 1.42rem;
  overflow: hidden;
  touch-action: none;

  .item-letter-list {
    &:before {
      content: '';
      position: absolute;
      top: 0;
      width: 25%;
      left: 25%;
      border-left: 0.02rem solid #eee;
      border-right: 0.02rem solid #eee;
      height: 100%;
    }

    &:after {
      content: '';
      position: absolute;
      top: 0;
      width: 25%;
      left: 75%;
      border-left: 0.02rem solid #eee;
      height: 100%;
    }
  }

  .item {
    overflow: hidden;
    height: 100%;

    .item-cities {
      overflow: hidden;
      background: #fff;
      height: 3.2rem;

      .item-cities-content {
        float: left;
        width: 33.33%;
        height: 0.8rem;
        color: #000;
        line-height: 0.8rem;
        text-align: center;
      }
    }

    .item-sort-list {
      overflow: hidden;
      background: #fff;

      .sort-list-content {
        width: 16.66%;
        float: left;
        height: 0.8rem;
        color: #000;
        line-height: 0.8rem;
        text-align: center;
      }
    }
  }

  .letter-list {
    position: relative;
    background: #fff;

    .item-letter-list {
      overflow: hidden;

      .item-letter-content {
        float: left;
        width: 25%;
        height: 0.8rem;
        line-height: 0.8rem;
        text-align: center;
      }
    }
  }

  .col {
    padding: 0.24rem 0.3rem;
    background: #eee;
  }
}
</style>