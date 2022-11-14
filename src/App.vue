<template>
  <header>
    <HeaderComponent />
  </header>
  <main>
    <MainComponent />
    <CharacterList :characters="CharacterList" />
  </main>
</template>

<script>
import axios from "axios";
import CharacterList from "./components/CharacterList.vue";
import HeaderComponent from "./components/HeaderComponent.vue";
import MainComponent from "./components/MainComponent.vue";
export default {
  components: {
    MainComponent,
    HeaderComponent,
    CharacterList,
  },
  data() {
    return {
      apiURL: "https://www.breakingbadapi.com/api/characters",
      CharacterList: [],
      loading: false,
    };
  },
  methods: {
    getCharacters() {
      this.loading = true;
      axios
        .get(this.apiURL)
        .then((res) => {
          console.log(res.data);
          this.CharacterList = [...res.data];
          console.log(this.CharacterList);
          this.loading = false;
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
  created() {
    this.getCharacters();
  },
};
</script>

<style lang="scss" scoped></style>
