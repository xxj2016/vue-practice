<template>
  <div class="users">
    <h1>你好啊, Users</h1>
    <ul>
        <li v-for="user in users">
            <h2>{{user.name}}</h2>
            <h3>{{user.username}}</h3>
        </li>
    </ul>
    <button v-on:click="deleteUser">删除</button>
  </div>
</template>
<!--
    传值： string number boolean
    引用： array object
-->
<script>
export default {
  name: 'users',
//   props: ["users"],
  props: {
      users: {
          type: Array,
          required: true
      }
  },
  data () {
    return {

    }
  },
  methods: {
      deleteUser: function() {
          this.users.pop();
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.users {
    width: 100%;
    max-width: 1200px;
    margin: 40px auto;
    padding: 0 20px;
    box-sizing: border-box;
}
ul {
    display: flex;
    flex-wrap: wrap;
    list-style-type: none;
    padding: 0;
}
li {
    flex-grow: 1;
    flex-basis: 200px;
    text-align: center;
    padding: 30px auto;
    margin: 10px;
    border: 1px solid #222;
}
</style>
