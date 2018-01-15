<template>
  <div id="home">
    <app-header v-on:titleChanged="updateTitle($event)" v-bind:title="title"></app-header>
    <users v-bind:users="users"></users>
    <users v-bind:users="users"></users>
    <app-footer v-bind:title="title"></app-footer>
  </div>
</template>

<script>
// 局部注册组件
import Users from "./Users";
import Header from "./Header";
import Footer from "./Footer";

export default {
  name: "Home",
  data() {
    return {
      // title: "这是我的第一个脚手架！"
      users: [
        { name: "Jet", position: "Web开发", show: false },
        { name: "Jet", position: "Web开发", show: false },
        { name: "Jet", position: "Web开发", show: false },
        { name: "Jet", position: "Web开发", show: false },
        { name: "Jet", position: "Web开发", show: false },
        { name: "Jet", position: "Web开发", show: false },
        { name: "Jet", position: "Web开发", show: false },
        { name: "Jet", position: "Web开发", show: false },
        { name: "Jet", position: "Web开发", show: false }
      ],
      title: "传入的时一个只[string，number,boolean]"
    };
  },
  methods: {
    updateTitle(title) {
      this.title = title;
    }
  },
  components: {
    users: Users,
    "app-header": Header,
    "app-footer": Footer
  }
};
</script>

<style scoped>
h1 {
  color: #c12f22;
}
</style>
