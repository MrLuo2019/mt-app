<template>
  <el-container class="layout-default">
    <el-header style="height:auto;">
      <my-header></my-header>
    </el-header>
    <el-main>
      <nuxt />
    </el-main>
    <el-footer style="height:auto;">
      <my-footer></my-footer>
    </el-footer>
  </el-container>
</template>

<script>
import myHeader from "@/components/public/header/index"
import myFooter from "@/components/public/footer/index"

export default {
  data() {
    return {}
  },

  components: {
    myHeader,
    myFooter
  },

  mounted(){},

  methods: {}
};
</script>

<style lang="scss">
@import "@/assets/css/public/layout.scss";
</style>