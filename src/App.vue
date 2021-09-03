<template>
  <div id="app">
    <v-app>
      <v-app-bar  dark app elevation="0">

      <template v-slot:img="{ props }">
        <v-img
          v-bind="props"
          gradient="to top right, rgba(100,115,201,.7), rgba(25,32,72,.7)"
        ></v-img>
      </template>
      9/7 公園下的前端工程師</v-app-bar>
      <v-main class="px-3">
        <div class="d-flex justify-center mt-8" v-if="isLoading">
          <v-progress-circular
            indeterminate
            :size="100"
            color="primary"
          ></v-progress-circular>

        </div>
        <v-card
          class="mx-auto"
          max-width="500"
          tile v-else
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
        <div class="mt-8 purple--text darken-1 d-flex justify-center">
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
    this.load()
  },
  data: () => ({
    items: [],
    isLoading: false
  }),
  methods: {
    async load () {
      try {
        this.isLoading = true
        const res = await axios.get('https://script.google.com/macros/s/AKfycbzFZpSdRLEq6-Rt2e64NSFzxZchdoxvg93ii7dr_8u2ij0ZU3xSfMxnzU38K3sXUFfy3w/exec')
        this.items = res.data
      } catch (err) {
        console.log('err', err)
      } finally {
        this.isLoading = false
      }
    }
  }
}
</script>

<style lang="scss">

</style>
