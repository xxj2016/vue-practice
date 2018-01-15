<template>
  <div id="translateForm">
      <form v-on:submit="formSubmit">
          <input type="text" v-model="transFormtext" placeholder="请输入你想翻译的东西">
          <select>
              <option value="en">English</option>
          </select>
          <input type="submit" value="提交">
      </form>
  </div>
</template>

<script>
export default {
  name: "translateForm",
  data: function() {
      return {
          transFormtext: ""
      }
  },
  methods: {
      formSubmit: function(e) {
          console.log(this.transFormtext);
          this.$emit("transFormText",this.transFormtext);
          e.preventDefault();
      }
  }
};
</script>

<style>

</style>
