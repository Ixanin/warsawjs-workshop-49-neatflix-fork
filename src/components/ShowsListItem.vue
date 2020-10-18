<template>
  <div
      class="shows-list-item"
      v-on:click="onClick"
      :style="{backgroundImage: `url(${show.imgURL})`}"
  >
    <div class="info-wrapper">
      <div v-if="!showSummary">
        <h2 class="title">{{show.name}}</h2>
        <div class="year-rating-wrapper">
          <div class="year">{{show.premiered}}</div>
          <div class="rating">{{show.rating}}</div>
        </div>
      </div>
      <p v-else>{{show.summary}}</p>
    </div>
  </div>
</template>

<script>
    export default {
        name: 'ShowsListItem',
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
        methods: {
            onClick() {
                this.showSummary = !this.showSummary;
            }
        }
    }
</script>

<style scoped lang="scss">
  .shows-list-item {
    text-align: center;
    display: flex;
    flex-direction: column-reverse;
    height: 300px;
    width: 200px;
    margin: 1vw;
    background: rgb(119, 7, 7);
    height: 300px;
    border: 2px solid;
    color: pink;
    background-repeat: no-repeat;
    background-size: cover;

    & .info-wrapper {
      background-color: black;
      color: white;

      & h2 {
        margin: 5px 0 0;
      }

      & .year-rating-wrapper {
        display: flex;
        flex-direction: row;
        justify-content: space-around;
      }

      & .rating {
        color: rgb(236, 213, 4);
        transform: scale(1.1);
        font-weight: bold;
      }
    }
  }

</style>