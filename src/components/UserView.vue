<template>
  <div>User View</div>
  <div v-for="project in allProjects" :key="project.title">
    <img :src="project.image" id="card-image" />
    <h3>{{ project.title }}</h3>
    <p>{{ project.description }}</p>
  </div>
</template>

<script>
export default {
  name: "UserView",
  props: ["projects"],
};
</script>

<style></style>
