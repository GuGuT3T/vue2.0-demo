<template>
  <div id="app">
    <img src="./assets/logo.png" alt="">
    <!-- 路由匹配到的组件将渲染在这里 -->
    <router-link :to="'apple'" tag='li'>Go to apple</router-link> // 可以传入字符串 tag指定li
    <router-link :to="{name:'banana',params:{testArr}}">Go to banana</router-link>
    <div @click="toBanana">跳转路由banana</div>
    <router-link :to="{path:'/red'}">Go to redBanana</router-link>
    <br>// 命名路由
    <!-- <router-link :to="{name:'applePage'}">Go to applePage</router-link> -->
    
    <router-view></router-view>
    <br>
    <router-view name="viewA"></router-view> // 命名视图
  </div>
  
</template>

<script>
export default {
  name: "app",
  components: {
    // hello
  },
  data () {
    return {
      testArr: {
        gyk: {
          id: 1
        },
        hb: {
          id: 2
        }
      },
    }
  },
   methods: {
        toBanana () {
          console.log(this.$router.push({path:'/banana',query: {testArr:this.testArr}}))
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
