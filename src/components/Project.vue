<template>
  <div>
    <h1>{{ name }}</h1>
    <img :src="imagePath" :alt="name">
    <h4>{{ description }}</h4>
  </div>
</template>

<script>
export default {
  name: "Project",
  props: {
    name: String,
    description: String,
    imagePath: String
  }
}
</script>

<style scoped>

</style>