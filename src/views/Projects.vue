<!--
  - Copyright (c) 2021. Robert Ciliberto
  -->

<template>
  <div class="projects">
    <h1>Projects</h1>
    <div
      class="project-cards"
      v-for="project in projectData"
      :key="project.name"
    >
      <project
        :name="project.name"
        :description="project.description"
        :image_src="project.image_src"
        :image_alt="project.image_alt"
        :site-link="project.site_link"
      />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Project, { ProjectProps } from "@/components/Project.vue";

import ciliberto_website from "@/assets/img/ciliberto_website.png";

export default defineComponent({
  data() {
    return {
      projectData: [
        {
          name: "Ciliber.to Website",
          description: "This website!",
          image_src: ciliberto_website,
          image_alt: "Ciliber.to Website",
          site_link: "https://google.com/",
        } as ProjectProps,
        {
          name: "Ciliber.to Website",
          description: "This website!",
          image_src: ciliberto_website,
          image_alt: "Ciliber.to Website",
          site_link: "https://google.com/",
        } as ProjectProps,
        {
          name: "Ciliber.to Website",
          description: "This website!",
          image_src: ciliberto_website,
          image_alt: "Ciliber.to Website",
          site_link: "https://google.com/",
        } as ProjectProps,
        {
          name: "Ciliber.to Website",
          description: "This website!",
          image_src: ciliberto_website,
          image_alt: "Ciliber.to Website",
          site_link: "https://google.com/",
        } as ProjectProps,
      ],
    };
  },
  name: "Projects",
  components: { Project },
});
</script>

<style scoped></style>
