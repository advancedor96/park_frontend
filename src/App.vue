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
    axios.get('https://script.googleusercontent.com/macros/echo?user_content_key=RQa3UV_bp_A7Ot7b2DI8pf30A6arE2OOTUcokNr27xbC3A-qT0h7SkFfNskX3AbNvZZdqKLHCGlBHlGwxlCpatVoL8S1QuYxm5_BxDlH2jW0nuo2oDemN9CCS2h10ox_1xSncGQajx_ryfhECjZEnCJAaF2O3DjeG585D8Kdya5ggRYxt5IwwZRB3qdeyKo-1Wiw_r0D52gFfrcngihQDv55RuLsdhyDMU741UnYodE3UJ8JiiR8kA&lib=MlIA8paqZQMOFrrZqMEnbFiq1-vRkhSuq')
      .then((response) => {
        // handle success
        console.log(response.data)
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
