<template>
  <div
      class="shows-list-item"
      :style="{backgroundImage: `url(${show.imgURL})`}"
      v-on:click="$emit('showDetails')"
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
        props: ['show', 'showSummary'],
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