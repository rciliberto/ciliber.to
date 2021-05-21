<!--
  - Copyright (c) 2021. Robert Ciliberto
  -->

<template>
  <div class="container" @click="onProjectClick">
    <h2>{{ name }}</h2>
    <img :src="image_src" :alt="image_alt" />
    <p>{{ description }}</p>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export interface ProjectProps {
  name: string;
  description: string;
  image_src: string;
  image_alt: string;
  site_link: string;
}

export default defineComponent({
  name: "Project",
  methods: {
    onProjectClick() {
      console.log(this.site_link);
      window.open(this.site_link);
    },
  },
  props: {
    name: String,
    description: String,
    image_src: String,
    image_alt: String,
    site_link: String,
  },
});
</script>

<style scoped>
.container {
  background-color: #333333;
  width: 23%;
  margin: 1%;
  float: left;
  padding-left: 1%;
  padding-right: 1%;
  box-sizing: border-box;
  border: 4px #888888 solid;
  border-radius: 20px;
}

.container:hover {
  cursor: pointer;
  background-color: #222222;
}

img {
  width: 100%;
}
</style>
