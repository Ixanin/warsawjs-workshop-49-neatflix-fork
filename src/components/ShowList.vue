<template>
  <div class="container">
    <div
        v-for="show in shows"
        :key="show.id"
    >
      <ShowsListItem
          :show="show"
          :showSummary="showSummary"
          v-on:showDetails="showDetails"
      />
    </div>
  </div>
</template>

<script>
    import ShowsListItem from '@/components/ShowsListItem';

    export default {
        name: 'ShowsList',
        components: {
            ShowsListItem
        },
        props: ['shows'],
        methods: {
            onClick() {
                this.showSummary = !this.showSummary;
            },
            showDetails(showId) {
                if (showId === this.showSummary) {
                    this.showSummary = false;

                } else {
                    this.showSummary = showId;
                }
            }
        },
        data() {
            return {
                showSummary: false,
            }
        },
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
  .container {
    display: flex;
  }

</style>