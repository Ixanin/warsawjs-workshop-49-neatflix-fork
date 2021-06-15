<template>
  <input
    aria-label="search"
    type="text"
    v-on:input="$emit('search', $event.target.value)"
    v-model="value"
  />
</template>

<script>
export default {
  name: "SearchInput",
  props: ["defaultValue"],
  data() {
    return {
      value: this.defaultValue,
    };
  },
};
</script>

<style scoped></style>
