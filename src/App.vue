<template>
  <header>
    <HeaderComponent />
  </header>
  <main>
    <MainComponent @filterchar="getCharacters" />
    <CharacterList :characters="CharacterList" />
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
    getCharacters(category) {
      let options = null;
      if (category) {
        options = {
          params: {
            category: category,
          },
        };
      }

      const apiURL = store.apiURL + this.endPoint;
      axios.get(apiURL, options).then((res) => {
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
