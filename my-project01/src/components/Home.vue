<template>
  <div id="home">
    <app-header></app-header>
    <users v-bind:users="users" v-bind:title="title"></users>
    <!-- <users v-bind:users="users"></users> -->
    <app-footer v-on:changeTitle="updateTitle($event)"></app-footer>
  </div>
</template>

<script>

// 局部注册组件
import Users from './Users'
import Header from './Header'
import Footer from './Footer'
export default {
  name: 'home',
  data(){
    return {
      title: "这是我的第一个Vue脚手架项目",
      users: [
        // { name: "Tom", positions: "java开发", show: false },
        // { name: "Tom", positions: "java开发", show: false },
        // { name: "Tom", positions: "java开发", show: false },
        // { name: "Tom", positions: "java开发", show: false },
        // { name: "Tom", positions: "java开发", show: false },
        // { name: "Tom", positions: "java开发", show: false },
        // { name: "Tom", positions: "java开发", show: false },
        // { name: "Tom", positions: "java开发", show: false },
        // { name: "Tom", positions: "java开发", show: false },
        // { name: "Tom", positions: "java开发", show: false }
      ]
    }
  },
  components:{
    // "users": Users
    "users": Users,
    "app-header": Header,
    'app-footer': Footer
  },
  methods: {
    updateTitle: function(title){
      this.title = title;
    }
  },
  created() {
      this.$http.get("https://jsonplaceholder.typicode.com/users")
      .then((data) => {
          this.users = data.body
      })
  }
}
</script>

<style>
h1{
  color: purple;
}
</style>
