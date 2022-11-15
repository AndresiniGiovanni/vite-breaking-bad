<template>
  <header>
    <HeaderComponent />
  </header>
  <main>
    <MainComponent @filterchar="getCharacters" />
    <CharacterList />
  </main>
</template>

<script>
import axios from "axios";
import CharacterList from "./components/CharacterList.vue";
import HeaderComponent from "./components/HeaderComponent.vue";
import MainComponent from "./components/MainComponent.vue";
import { store } from "./store";
export default {
  components: {
    MainComponent,
    HeaderComponent,
    CharacterList,
  },
  data() {
    return {
      store,
      endPoint: "characters",
    };
  },
  methods: {
    getCharacters() {
      if (store.searchStatus) {
        option = {
          params: {
            category: store.searchStatus,
          },
        };
      }

      const apiURL = store.apiURL + this.endPoint;
      axios.get(apiURL).then((res) => {
        store.CharacterList = res.data;
      });
    },
  },
  created() {
    this.getCharacters();
  },
};
</script>

<style lang="scss" scoped></style>
