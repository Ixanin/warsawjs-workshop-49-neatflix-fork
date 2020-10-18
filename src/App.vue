<template>
  <div id="app">
    <ShowsList :shows="shows"/>
  </div>
</template>
------------------------------------------------------
<script>
import ShowsList from '@/components/ShowList'

export default {
  name: 'App',
  components: {
    ShowsList
  },
  methods: {

  },
  // computed: {},
  // watch: {},

    data() {
        return {
            shows: [
                {
                    id: '1',
                    name: 'Kipo and the Age of Wonderbeasts',
                    premiered: 2019, // rok premiery
                    rating: 10, // ocena, 0 - 10
                    imgURL: 'https://image.tmdb.org/t/p/original/v7i8qBl5WKJHEh0z0omAdGwvso7.jpg',
                    summary: 'Kipo, a sheltered girl, gets a crash course in survival when a mutant attack sends her to the surface, far from the safety of her underground home.'
                },
                {
                    id: '2',
                    name: 'Kipo and the Age of Wonderbeasts',
                    premiered: 2019, // rok premiery
                    rating: 10, // ocena, 0 - 10
                    imgURL: 'https://image.tmdb.org/t/p/original/v7i8qBl5WKJHEh0z0omAdGwvso7.jpg',
                    summary: 'Kipo, a sheltered girl, gets a crash course in survival when a mutant attack sends her to the surface, far from the safety of her underground home.'
                }
            ],
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
