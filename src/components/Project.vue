<!--
  - Copyright (c) 2021. Robert Ciliberto
  -->

<template>
  <div class="project" @click="onProjectClick">
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
  siteLink: string;
}

export default defineComponent({
  name: "Project",
  methods: {
    onProjectClick: () => {
      window.open("");
    },
  },
  props: {
    name: String,
    description: String,
    image_src: Image,
    image_alt: String,
    siteLink: String,
  },
});
</script>

<style scoped>
.project {
  background-color: #333333;
  width: 20%;
  margin: 10px 10px;
  border: 4px #888888 solid;
  float: left;
  border-radius: 20px;
}

.project:hover {
  cursor: pointer;
  background-color: #222222;
}
</style>
