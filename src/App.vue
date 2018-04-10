<template>
  <div id="app">
    <img src="./assets/logo.png" alt="">
    {{ totalPrice }}
    <apple></apple>
    <banana></banana>
  </div>
  
</template>

<script>
import Apple from './components/apple'
import Banana from './components/banana'
export default {
  name: "app",
  components: {
    Apple,Banana
  },
  computed: { //计算属性
    totalPrice () {
      return this.$store.state.totalPrice
      // return this.$store.getter.getTotal //从getter获取
    }
  }
};
</script>

<style>
html {
  width: 100%;
  height: 100vh;
}
.fade-enter-active,
.fade-leave-active {
  transition: all 0.5s ease-out;
}
.fade-enter,
.fade-leave-active {
  opacity: 0;
}

.my-trans-leave-active,
.my-trans-enter-active {
  transition: all 0.5s ease-out;
}
.my-trans-enter {
  transform: translateY(-500px);
  opacity: 0;
}
.my-trans-leave-active {
  transform: translateY(500px);
  opacity: 0;
}
</style>
