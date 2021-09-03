<template>
  <div id="app">
    <v-app>
      <v-app-bar app>9/7 公園下的前端工程師</v-app-bar>
      <v-main>
        <v-card
          class="mx-auto"
          max-width="300"
          tile
        >
          <v-list dense>
              <v-list-item
                v-for="(item, i) in items"
                :key="i"
                three-line
              >
                <v-list-item-icon>
                  <v-icon v-text="`mdi-account`"></v-icon>
                </v-list-item-icon>
                <v-list-item-content>
                  <v-list-item-title>{{ item[0]? item[0] : '空' }}</v-list-item-title>
                  <v-list-item-subtitle>
                    想知道的：{{ item[1]? item[1] : '空' }}
                  </v-list-item-subtitle>
                  <v-list-item-subtitle>
                    能給的：{{ item[2]? item[2] : '空' }}
                  </v-list-item-subtitle>
                </v-list-item-content>
              </v-list-item>
          </v-list>
        </v-card>
        <div style="text-align: center;">
          活動詳情：<br/>
          <a href="https://fb.me/e/2L9wRl9A3">https://fb.me/e/2L9wRl9A3</a>
        </div>
      </v-main>
    </v-app>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'App',
  components: {
  },
  created () {
    // https://script.googleusercontent.com/macros/echo?user_content_key=RQa3UV_bp_A7Ot7b2DI8pf30A6arE2OOTUcokNr27xbC3A-qT0h7SkFfNskX3AbNvZZdqKLHCGlBHlGwxlCpatVoL8S1QuYxm5_BxDlH2jW0nuo2oDemN9CCS2h10ox_1xSncGQajx_ryfhECjZEnCJAaF2O3DjeG585D8Kdya5ggRYxt5IwwZRB3qdeyKo-1Wiw_r0D52gFfrcngihQDv55RuLsdhyDMU741UnYodE3UJ8JiiR8kA&lib=MlIA8paqZQMOFrrZqMEnbFiq1-vRkhSuq

    axios.get('https://script.google.com/macros/s/AKfycbzFZpSdRLEq6-Rt2e64NSFzxZchdoxvg93ii7dr_8u2ij0ZU3xSfMxnzU38K3sXUFfy3w/exec')
      .then((response) => {
        // handle success
        console.log(response.data)
        this.items = response.data
      })
      .catch(function (error) {
        // handle error
        console.log(error)
      })
      .then(function () {
        // always executed
      })
  },
  data: () => ({
    items: []
  })
}
</script>

<style lang="scss">

</style>
