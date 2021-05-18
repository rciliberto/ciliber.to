<template>
  <div class="projects">
    <h1>Projects</h1>
    <Project name="Ciliber.to Website" description="This website!"></Project>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Project from "@/components/Project.vue";

export default defineComponent({
  name: "Projects",
  components: { Project },
});
</script>

<style scoped></style>
