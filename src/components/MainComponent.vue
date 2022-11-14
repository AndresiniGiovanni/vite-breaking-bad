<template>
  <main class="container">
    <select class="form-select my-select" aria-label="">
      <option selected>Select Category</option>
      <option value="1">One</option>
      <option value="2">Two</option>
      <option value="3">Three</option>
    </select>

    <section class="container bg-light mt-3">
      <div class="characters-found text-white">test</div>
      
    </section>
  </main>
</template>

<script>
import '../assets/styles/partials/_variables.scss'
export default {};
</script>

<style lang="scss" scoped>
.my-select {
  width: 13%;
}

</style>
