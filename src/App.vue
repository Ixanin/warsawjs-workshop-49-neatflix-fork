<template>
  <div id="app">
    <SearchInput
        default-value=""
        v-on:search="search"
    />
    <ShowsList :shows="matched"/>
  </div>
</template>
------------------------------------------------------
<script>
    import ShowsList from '@/components/ShowList'
    import SearchInput from './components/SearchInput';

    export default {
        name: 'App',
        components: {
            SearchInput,
            ShowsList,
        },
        methods: {
            search(query) {
                this.query = query;
            }
        },
        computed: {
            matched: function () {
                const str = this.query.toLowerCase();

                return this.shows
                    .filter(show => show.name.toLowerCase().includes(str))
            },
        },
        // watch: {},

        data() {
            return {
                query: '',
                shows: [{
                    id: '1',
                    name: 'True Detective',
                    premiered: 2014,
                    rating: 10,
                    imgURL: 'http://static.tvmaze.com/uploads/images/medium_portrait/178/445621.jpg',
                    summary: 'Tak, to jest po prostu świetny serial, no. Bardzo polecam',
                }, {
                    id: '2',
                    name: 'House Of Cards',
                    premiered: 2013,
                    rating: 10,
                    imgURL: 'http://static.tvmaze.com/uploads/images/medium_portrait/169/424482.jpg',
                    summary: 'Ojej, no ten to wyjątkowo, taki Thriller Polityczny najwyższych lotów.',
                }, {
                    id: '3',
                    name: 'Berserk',
                    premiered: 1997,
                    rating: 9,
                    imgURL: 'http://static.tvmaze.com/uploads/images/medium_portrait/0/249.jpg',
                    summary: 'Kolega mówi, że to świetne animbo, ale trochę się cykam',
                }, {
                    id: '4',
                    name: 'Rick and Morty',
                    premiered: 2013,
                    rating: 9,
                    imgURL: 'http://static.tvmaze.com/uploads/images/medium_portrait/1/3603.jpg',
                    summary: 'A to jest o takim tym, dziadku co jest ogórkiem czy coś',
                }, {
                    id: '5',
                    name: 'Conan',
                    premiered: 2010,
                    rating: 8,
                    imgURL: 'http://static.tvmaze.com/uploads/images/medium_portrait/1/4583.jpg',
                    summary: 'Śmieszny pan taki.',
                }, {
                    name: 'The Daily Show with Jon Stewart',
                    premiered: 1999,
                    rating: 10,
                    imgURL: 'http://static.tvmaze.com/uploads/images/medium_portrait/1/4598.jpg',
                    summary: 'Inny śmieszny Pan',
                },]
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
