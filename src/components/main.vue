<template>
  <div class="main">
    <transition name="fade" mode="out-in">
      <router-view></router-view>
    </transition>
    <v-navbar :tabs="tabs"></v-navbar>
  </div>
</template>

<script>
  import Navbar from './navbar.vue'

  export default {
    name: 'main',
    props: {
      tabs: {
        type: Array
      }
    },
    components: {
      "v-navbar": Navbar
    }
  }
</script>


<style rel="stylesheet/scss" lang="scss">
  .fade-enter-active, .fade-leave-active {
    transition: opacity .5s ease;
  }

  .fade-enter, .fade-leave-active {
    opacity: 0
  }

  .child-view {
    position: absolute;
    transition: all .5s cubic-bezier(.55, 0, .1, 1);
  }

  .slide-left-enter, .slide-right-leave-active {
    opacity: 0;
    -webkit-transform: translate(30px, 0);
    transform: translate(30px, 0);
  }

  .slide-left-leave-active, .slide-right-enter {
    opacity: 0;
    -webkit-transform: translate(-30px, 0);
    transform: translate(-30px, 0);
  }
</style>
