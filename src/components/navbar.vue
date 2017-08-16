<template>
  <div class="nabbar-content">
    <span class="nav-item" v-for="item in tabs">
      <router-link :to="item.url">
        <img :src="item.icon">
        {{item.text}}
      </router-link>
    </span>
  </div>
</template>
<script>
  export default {
    props: {
      tabs: {
        type: Array
      }
    }
  }
</script>
<style rel="stylesheet/scss" lang="scss">
  .nabbar-content {
    position: fixed;
    left: 0;
    right: 0;
    bottom: 0;
    border-top: 1px solid #2c3e50;
    height: 50px;
    line-height: 50px;
  }

  .nav-item {
    display: inline-block;
    width: 25%;
    text-align: center;
    float: left;
    img {
      width: 22px;
      height: 22px;
    }
  }

  .nav-item a {
    color: #2c3e50;
    text-decoration: none;
  }

  .nav-item a.router-link-exact-active {
    color: #3399FF;
  }
</style>
