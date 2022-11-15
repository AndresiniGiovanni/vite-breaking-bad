<template>
  <main class="container">
    <form @submit.prevent="searchCharacters">
      <select
        value=""
        class="form-select my-select mb-4"
        aria-label=""
        v-model="store.searchStatus"
      >
        <option selected>Select Category</option>
        <option
          :value="item"
          v-for="(item, index) in categoryOption"
          :key="index"
        >
          {{ item }}
        </option>
      </select>
    </form>
  </main>
</template>

<script>
import { store } from "../store";
export default {
  data() {
    return {
      store,
      categoryOption: ["Breaking Bad", "Better Call Saul"],
    };
  },
  methods: {
    searchCharacters() {
      this.$emit("filterchar");
    },
  },
};
</script>

<style lang="scss" scoped>
@use "../assets/styles/partials/variables" as *;
.my-select {
  width: 13%;
}
</style>
