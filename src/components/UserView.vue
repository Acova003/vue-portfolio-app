<template>
  <!-- Featured Image Section -->
  <section class="featured-section">
    <div id="featured-card" class="card">
      <div class="container">
        <figure class="featured-image">
          <img :src="featured.image" :alt="featured.title" />
        </figure>
        <div class="text-content">
          <h1 class="title">{{ featured.title }}</h1>
          <div class="content">{{ featured.description }}</div>
        </div>
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
.container {
  display: flex;
  align-items: center;
}
.featured-section {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 5%;
  max-width: 80%;
  margin-left: auto;
  margin-right: auto;
}

.featured-image {
  height: auto;
  max-height: 800px;
  object-fit: cover;
}

.featured-image,
.text-content {
  width: 45%;
}

@media screen and (max-width: 600px) {
  .container {
    flex-direction: column;
  }

  .featured-image,
  .text-content {
    width: 100%;
  }
}

#featured-card {
  background-color: rgb(255, 241, 241);
}
.title {
  margin-top: 2rem;
  margin-bottom: 2rem;
  margin-left: 2rem;
  margin-right: 2rem;
}
</style>
