<template>
  <div class="container">
    <div class="card">
      <div class="card-content">
        <div class="content">
          <form @submit.prevent="handleSubmit">
            <label class="label">Title</label>
            <input
              class="input"
              v-model="title"
              type="text"
              placeholder="Project 1"
            />

            <label class="label">Image</label>
            <input
              class="input"
              v-model="image"
              type="text"
              placeholder="linktoimage.com"
            />

            <label class="label">Description</label>
            <textarea
              class="textarea"
              v-model="description"
              placeholder="Project description"
            ></textarea>
            <div>
              <button
                type="handleSubmit"
                id="submit-btn"
                class="button is-primary"
              >
                SUBMIT
              </button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AdminView",
  data() {
    return {
      title: "",
      image: "",
      description: "",
    };
  },
  methods: {
    handleSubmit() {
      this.$emit("createProject", {
        title: this.title,
        image: this.image,
        description: this.description,
      });

      // Clear the form
      this.title = "";
      this.image = "";
      this.description = "";
    },
  },
};
</script>

<style>
form {
  display: flex;
  flex-direction: column;
  width: 50%;
  margin: 0 auto;
}

#submit-btn {
  margin-top: 10px;
}

#card-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
</style>
