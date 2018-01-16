<template>
    <div class="row" id="translateForm">
        <div class="col-md-6 offset-3">
            <form id="transform" class="alert alert-dismissible alert-warning form-inline" v-on:submit="formSubmit">
                <input class="form-control" type="text" v-model="transFormtext" placeholder="请输入你想翻译的东西">
                <select class="form-control" v-model="language">
                    <option value="en">English</option>
                    <option value="ru">Russian</option>
                    <option value="zh">Chinese</option>
                    <option value="ja">Japanese</option>
                    <option value="th">Thai</option>
                    <option value="fr">French</option>
                    <option value="it">Italian</option>
                </select>
                <input class="btn btn-primary" type="submit" value="提交">
            </form>
        </div>

    </div>
</template>

<script>
export default {
  name: "translateForm",
  data: function() {
    return {
      transFormtext: "",
      language: ""
    };
  },
  created: function() {
    this.language = "en";
  },
  methods: {
    formSubmit: function(e) {
      console.log(this.transFormtext);
      this.$emit("transFormText", this.transFormtext, this.language);
      e.preventDefault();
    }
  }
};
</script>

<style>
#transform {
    border: 1px solid #ccc;
    border-radius: 10px;
}
</style>
