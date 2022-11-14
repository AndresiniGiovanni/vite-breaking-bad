<template>
  <div class="container">
    <div class="row d-flex justify-content-center">
      <div class="col-lg-2 col-md-6 card">
        <div
          class="character"
          v-for="(item, index) in characters"
          key="item.char_id"
        >
          <img :src="item.img" alt="" />
          <h3>{{ item.name }}</h3>
          <div></div>
          <p></p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "characterList",
  props: ["characters"],
};
</script>

<style lang="scss" scoped></style>
