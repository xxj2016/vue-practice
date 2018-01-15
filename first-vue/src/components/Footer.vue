<template>
    <footer>
        <p>{{CopyRight}} {{title}}</p>
    </footer>
</template>

<script>
export default {
  name: "app-footer",
  props: {
    title: {
      type: String
    }
  },
  data() {
    return {
      CopyRight: "CopyRight 2017 Vue Demo"
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
footer {
  background-color: #222;
  color: lightgreen;
  padding: 10px;
}
p {
  text-align: center;
}
</style>
