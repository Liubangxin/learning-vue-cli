<template>
  <div class="footer">
      <p> {{copyright}} </p>
      <button v-on:click="changeTitle">点击</button>
  </div>
</template>

<script>
export default {
  name: 'app-footer',
  data () {
    return {
      copyright: "Copyright 2018 Vue Demo"
    }
  },
  methods: {
    changeTitle: function(){
      this.$emit("changeTitle", "子向父传值")
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.footer{
    background: #222;
    padding: 6px;
}
p{
    color: lightgreen;
    text-align: center;
}
</style>
