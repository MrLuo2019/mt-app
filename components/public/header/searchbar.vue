<template>
  <div class="search-panel">
    <el-row class="m-header-searchbar">
      <el-col class="left" :span="3">
        <img src="//s0.meituan.net/bs/fe-web-meituan/fa5f0f0/img/logo.png" alt="美团" />
      </el-col>
      <el-col class="center" :span="15">
        <div class="wrapper">
          <el-input
            placeholder="搜索商家或地点"
            v-model="search"
            @focus="focus"
            @blur="blur"
            @input="input"
          ></el-input>
          <el-button type="primary" icon="el-icon-search"></el-button>
          <dl class="hotPlace" v-if="isHotPlace">
            <dt>热门搜索</dt>
            <dd v-for="(item, index) in hotPlace" :key="index">{{item}}</dd>
          </dl>
          <dl class="searchList" v-if="isSearchList">
            <dt>热门搜索</dt>
            <dd v-for="(item, index) in searchList" :key="index">{{item}}</dd>
          </dl>
        </div>
        <p class="suggset">
          <a href="#">故宫博物院</a>
          <a href="#">故宫博物院</a>
          <a href="#">故宫博物院</a>
          <a href="#">故宫博物院</a>
        </p>
        <ul class="nav">
          <li>
            <nuxt-link class="tackout" to="/">美团外卖</nuxt-link>
          </li>
          <li>
            <nuxt-link class="movie" to="/">猫眼电影</nuxt-link>
          </li>
          <li>
            <nuxt-link class="hotel" to="/">美团酒店</nuxt-link>
          </li>
          <li>
            <nuxt-link class="apartment" to="/">名宿公寓</nuxt-link>
          </li>
          <li>
            <nuxt-link class="business" to="/">商家入驻</nuxt-link>
          </li>
        </ul>
      </el-col>
      <el-col class="right" :span="6">
        <ul class="security">
          <li>
            <i class="refund"></i>
            <p>随时退</p>
          </li>
          <li>
            <i class="single"></i>
            <p>不满意免单</p>
          </li>
          <li>
            <i class="overdue"></i>
            <p>过期退</p>
          </li>
        </ul>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  data () {
    return {
      search: "",
      isFocus: false,
      hotPlace: ["火锅", "火锅", "火锅", "火锅"],
      searchList: ["火锅", "火锅", "火锅", "火锅"]
    };
  },

  components: {},

  computed: {
    isHotPlace: function () {
      return this.isFocus && !this.search
    },
    isSearchList: function () {
      return this.isFocus && this.search
    }
  },

  mounted () { },

  methods: {
    focus: function () {
      this.isFocus = true
    },
    blur: function () {
      let self = this

      setTimeout(function () {
        self.isFocus = false
      }, 200)
    },
    input: function () {
      
    }
  }
}
</script>

<style lang="scss">
@import '@/assets/css/public/header/search.scss';
</style>
