<template>
  <div id="app">
    hi
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'App',
  components: {
  },
  created () {
    axios.get('https://script.google.com/macros/s/AKfycbykQJoo2tIjlegugf6AyBJfQUEjOWeeFtEMl88H59w/dev')
      .then(function (response) {
        // handle success
        console.log(response)
      })
      .catch(function (error) {
        // handle error
        console.log(error)
      })
      .then(function () {
        // always executed
      })
  }
}
</script>

<style lang="scss">

</style>
