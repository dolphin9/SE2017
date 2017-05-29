<template>
<div id="box">
<span>Search Page</span>
<input type="button" @click="get()" value="按钮">
</div>
</template>
<script>
// json
module.exports = {
  data () {
    return {
      msg: 'Hello World!'
    }
  },
  methods: {
    get: function () {
// 发送get请求
      this.$http.get('/src/get.php', {params: {abc: 1, def: 2}}).then(function (res) {
        alert(res.body)
      }, function (res) {
        console.log(res.status)
      })
    }
  }
}
</script>
<style scoped>

 </style>
