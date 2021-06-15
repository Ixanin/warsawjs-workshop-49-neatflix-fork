<template>
  <div class="container">
    <div v-for="show in shows" :key="show.id">
      <ShowsListItem
        :show="show"
        :showSummary="showSummary"
        v-on:showDetails="showDetails"
      />
    </div>
  </div>
</template>

<script>
import ShowsListItem from "@/components/ShowsListItem";

export default {
  name: "ShowsList",
  components: {
    ShowsListItem,
  },
  props: ["shows"],
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
    },
  },
  data() {
    return {
      showSummary: false,
    };
  },
};
</script>

<style scoped lang="scss">
.container {
  display: flex;
  flex-wrap: wrap;
}
</style>
