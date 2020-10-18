<template>
  <div id="app">
    <ShowsListItem
        :show="show"
        :showSummary="showSummary"
        v-on:showDetails="showDetails"
    />
  </div>
</template>
------------------------------------------------------
<script>
import ShowsListItem from '@/components/ShowsListItem'

export default {
  name: 'App',
  components: {
    ShowsListItem
  },
  methods: {
      showDetails() {
          this.showSummary = !this.showSummary;
      }
  },
  // computed: {},
  // watch: {},

    data() {
        return {
            showSummary: false,
            show: {
                name: 'Kipo and the Age of Wonderbeasts',
                premiered: 2019, // rok premiery
                rating: 10, // ocena, 0 - 10
                imgURL: 'https://image.tmdb.org/t/p/original/v7i8qBl5WKJHEh0z0omAdGwvso7.jpg',
                summary: 'Kipo, a sheltered girl, gets a crash course in survival when a mutant attack sends her to the surface, far from the safety of her underground home.'
            },
        }
    },
  // created() {},
  // destroyed() {},
}
</script>
------------------------------------------------------
<style lang="scss">
html,
body {
  margin: 0;
  padding: 0;
}
* {
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  color: #2c3e50;
  height: 100vh;
  width: 100vw;
  .shows-list {
    padding: 15px;
  }
}
</style>
