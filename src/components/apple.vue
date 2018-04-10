<template>
  <div class="hello">
      <h1>{{msg}}</h1>
      <p>{{ $route.params.color }}</p>
      <button @click="getParam">get param</button>
      <br>
      // vuex Demo
      {{price}}
      <button @click="addOne">add</button>
      <button @click="minusOne">minus</button>
  </div>
</template>
<script>
export default {
  name: 'hello',
  data() {
    return {
      msg: 'i am apple',
      price: 5,
    }
  },
  methods: {
    getParam () {
      console.log(this.$route.params) // 注入之后可以直接使用
    },
    addOne () {
      this.$store.dispatch('increment',this.price);
    },
    minusOne () {
      this.$store.commit('decrement',this.price);
    },
  }
};
</script>

