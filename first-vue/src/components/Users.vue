<template>
  <div class="users">
    <h1>你好啊, Users</h1>
    <ul>
        <li v-for="user in users" 
            v-on:click="user.show = !user.show">
            <h1>{{user.name}}</h1>
            <h2 v-if="user.show">{{user.position}}</h2>
        </li>
    </ul>
    <button v-on:click="deleteUser">删除</button>
  </div>
</template>

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
