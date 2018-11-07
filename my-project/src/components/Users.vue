<template>
  <div class="users">
      <ul>
          <li v-for="u in users" 
            v-on:click="u.show=!u.show">        
              <h2> {{u.name}} </h2>
              <h3 v-show="u.show"> {{u.positions}} </h3>
             
          </li>
      </ul>

      <button v-on:click="deleteUser"> {{title}} </button>
  </div>
</template>

<script>
export default {
  name: "users",
  // props: ["users"],
  props: {
    users: {
      type: Array,
      required: true
    },
    title: {
      type: String,
      required: true
    }
  },
  data() {
    return {};
  },
  methods: {
    deleteUser: function() {
      this.users.pop();
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
ul {
  display: flex;
  flex-wrap: wrap;
  list-style-type: none;
  padding: 0%;
}
li {
  flex-grow: 1;
  background: lightblue;
  border: 1px solid black;
  margin: 20px;
  padding: 30px;
  text-align: center;
}
</style>
