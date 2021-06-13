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
          description:
            "This website! Built using only Vue 3 with TypeScript. I started this project on the side to exercise and practice web development. It also serves as a great place to showcase what I am working on currently.",
          image_src: ciliberto_website,
          image_alt: "Ciliber.to Website",
          site_link: "https://github.com/rciliberto/ciliber.to",
        } as ProjectProps,
        {
          name: "Home Server",
          description:
            "I bought a used Dell R820 server to self host all my projects. It runs Debian with Proxmox virtualization and I have virtual machines for various purposes such as PfSense gateway firewall, NGNIX reverse proxy, Jenkins CI/CD, Docker applications, and Home Assistant home automation among others.",
          image_src: home_server,
          image_alt: "Picture of Robby with the server",
          site_link: undefined,
        } as ProjectProps,
        {
          name: "Blabber Generator",
          description:
            'My fiancée was making a short film for her film class and required gibberish voices for the characters in it. Rather than pull some audio clips off of the internet I decided to help her by creating a generator that can create similar voices to those seen in the video game "Animal Crossing." the voices implemented in the generator are made by making a sped up recording for how each letter of the alphabet sounds. This is combined for each letter in a sentence to create gibberish that sounds kind of like the inputted sentence.',
          image_src: "",
          image_alt: "GUI for Blabber Generator",
          site_link: "https://github.com/rciliberto/Blabber-Generator",
        } as ProjectProps,
        {
          name: "WikiWhere",
          description:
            "A project me and my friends came up with at HackHarvard 2019. It visualizes the shortest path from one Wikipedia page to another when navigating only by links to other pages in the content of each page.",
          image_src: "",
          image_alt: "Wikiwhere website",
          site_link: "https://github.com/wikiwhere/wikiwhere",
        } as ProjectProps,
      ],
    };
  },
  name: "Projects",
  components: { Project },
});
</script>

<style scoped></style>
