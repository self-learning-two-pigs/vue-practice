<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
import axios from 'axios'
axios.defaults.baseURL = '/api'
axios.defaults.headers['Content-Type'] = 'application/json;charset=UTF-8'
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  methods: {
    initData () {
      axios.get('/object-test')
        .then(function (respone) {
          console.log(respone)
        })
        .catch(function (error) {
          console.log(error)
        })
    }
  },
  created () {
    this.initData()
  }
}
</script>

<style scoped>
h1, h2 {
  font-weight: normal;
}
</style>
