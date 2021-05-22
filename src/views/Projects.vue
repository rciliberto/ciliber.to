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
        :site_link="project.site_link"
      />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Project, { ProjectProps } from "@/components/Project.vue";

import ciliberto_website from "@/assets/img/ciliberto_website.png";
import home_server from "@/assets/img/home_server.png";

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
          name: "Home Server",
          description: "Home Server ",
          image_src: home_server,
          image_alt: "Home Server Dashboard",
          site_link: undefined,
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
          description:
            'Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. Richard McClintock, a Latin professor at Hampden-Sydney College in Virginia, looked up one of the more obscure Latin words, consectetur, from a Lorem Ipsum passage, and going through the cites of the word in classical literature, discovered the undoubtable source. Lorem Ipsum comes from sections 1.10.32 and 1.10.33 of "de Finibus Bonorum et Malorum" (The Extremes of Good and Evil) by Cicero, written in 45 BC. This book is a treatise on the theory of ethics, very popular during the Renaissance. The first line of Lorem Ipsum, "Lorem ipsum dolor sit amet..", comes from a line in section 1.10.32.',
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
