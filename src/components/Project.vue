<template>
  <h1>{{ name }}</h1>
  <h2>{{ description }}</h2>
  <img src="{{ imagePath }}" alt="{{ name }}">

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