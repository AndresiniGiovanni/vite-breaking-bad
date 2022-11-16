<template>
  <main class="container">
    <form @submit.prevent="searchCharacters">
      <select
        value=""
        class="form-select my-select mb-4"
        aria-label=""
        v-model="store.searchStatus"
        @change="searchCharacters"
      >
        <option selected>Select Category</option>
        <option
          :value="category"
          v-for="(category, index) in categoryOption"
          :key="index"
        >
          {{ category }}
        </option>
      </select>
    </form>
  </main>
</template>

<script>
import { store } from "../store";
export default {
  name: "MainComponent",
  data() {
    return {
      store,
      categoryOption: ["Breaking Bad", "Better Call Saul"],
    };
  },
  methods: {
    searchCharacters() {
      console.log(store.searchStatus);
      this.$emit("filterchar", store.searchStatus);
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
