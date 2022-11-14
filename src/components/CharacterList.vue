<template>

  <section>
    <div class="container-fluid my-cont bg-white">
  <div class="container bg-light pt-4 char-cont">
    <div class="characters-found text-white">coming soon</div>
  </div>
      <div class="row d-flex justify-content-center">
        <div
          class="col-lg-2 col-md-6 card border-0 rounded-0 p-2 my-card m-2"
          v-for="(item, index) in characters"
          key="item.char_id"
        >
          <img :src="item.img" alt="" />
          <h5 class="text-white text-center mt-2">{{ item.name }}</h5>
          <div class="my-color text-center">{{ item.category }}</div>
          <p class="my-color text-center">{{ item.status }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "characterList",
  props: ["characters"],
};
</script>

<style lang="scss" scoped>
@use "../assets/styles/partials/variables" as *;

.characters-found{
    margin: 0 auto;
    width: 100%;
    height: 40px;
}
.my-cont
 {
  width: 70%;
}

.my-card {
  background-color: $bluegray;
}
.my-color{
    color: $textgray;
}
</style>
