<!--
  - Copyright (c) 2021. Robert Ciliberto
  -->

<template>
  <div>
    <h2>{{ name }}</h2>
    <img :src="imagePath" :alt="name" />
    <p>{{ description }}</p>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "Project",
  props: {
    name: String,
    description: String,
    imagePath: String,
  },
});
</script>

<style scoped></style>
