<template>
  <main class="container ">
    <select class="form-select my-select mb-4 " aria-label="">
      <option selected>Select Category</option>
      <option value="1">One</option>
      <option value="2">Two</option>
      <option value="3">Three</option>
    </select>

   
  </main>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@use "../assets/styles/partials/variables" as *;

.my-select {
  width: 13%;
}

</style>
