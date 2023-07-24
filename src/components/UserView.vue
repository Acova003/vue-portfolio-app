<template>
  <!-- Featured Image Section -->
  <section class="featured-section">
    <div id="featured-card" class="card">
      <div class="container">
        <h1 class="title">{{ featured.title }}</h1>
        <figure class="featured-image">
          <img :src="featured.image" :alt="featured.title" />
        </figure>
        <div class="content">{{ featured.description }}</div>
      </div>
    </div>
  </section>

  <!-- Grid of Projects -->
  <div class="columns is-multiline">
    <div class="column is-one-third" v-for="(project, i) in projects" :key="i">
      <div class="card">
        <div class="card-image">
          <figure class="image is-4by3">
            <img
              :src="project.image"
              :alt="project.title"
              @click="featured = project"
            />
          </figure>
        </div>
        <div class="card-content">
          <div class="media">
            <div class="media-content">
              <p class="title is-4">{{ project.title }}</p>
              <p class="subtitle is-6">{{ project.subtitle }}</p>
            </div>
          </div>
          <div class="content">
            {{ project.description }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "UserView",
  props: ["projects"],
  data() {
    return {
      featured: this.projects[0],
    };
  },
};
</script>

<style>
.featured-section {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 3rem; /* Add more padding to make the section bigger */
  margin-bottom: 2rem;
  max-width: 80%; /* You can adjust this value to make the section bigger or smaller */
  margin-left: auto;
  margin-right: auto;
}

.featured-image img {
  width: auto;
  height: auto; /* This ensures the image maintains its aspect ratio */
  max-height: 800px;
  object-fit: cover;
  margin-left: 2rem;
  margin-right: 2rem;
}

#featured-card {
  background-color: rgb(255, 241, 241);
}
.title {
  margin-top: 2rem;
  margin-bottom: 2rem;
}
</style>
