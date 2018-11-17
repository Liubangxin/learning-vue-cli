<template>
  <div id="app">
    <!-- <a href="#/">home</a> -->
    <!-- <a href="#/helloworld">helloworld</a> -->
    
    
    <ul>
      <li><router-link to='/'> home </router-link></li>
      <li><router-link to='/helloworld'> helloworld </router-link></li>
    </ul>
    <router-view/>
  </div>
</template>

<script>

// 局部注册组件
import Users from './components/Users'
import Header from './components/Header'
import Footer from './components/Footer'
export default {
  name: 'app'
}
</script>

<style>
h1{
  color: purple;
}
</style>
