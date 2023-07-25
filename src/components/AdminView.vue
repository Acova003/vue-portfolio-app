<template>
  <div class="container">
    <div class="card">
      <div class="card-content">
        <div class="form-container content">
          <form @submit.prevent="handleSubmit">
            <div class="field-container">
              <div class="field">
                <label class="label">Title</label>
                <input
                  class="input"
                  v-model="title"
                  type="text"
                  placeholder="Project 1"
                />
              </div>
              <div class="field">
                <label class="label">Image</label>
                <input
                  class="input"
                  v-model="image"
                  type="text"
                  placeholder="linktoimage.com"
                />
              </div>
            </div>
            <div class="field">
              <label class="label">Description</label>
              <textarea
                class="textarea"
                v-model="description"
                placeholder="Project description"
              ></textarea>
            </div>
            <div class="field">
              <button type="submit" id="submit-btn" class="button is-primary">
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
.container {
  display: flex;
  justify-content: center;
}

form {
  display: flex;
  flex-direction: column;
  margin: 0 auto;
}

.card {
  align-items: center;
}

#submit-btn {
  margin-top: 10px;
}
.field-container {
  display: flex;
  justify-content: space-between;
}

.field {
  flex: 1 1 auto;
  margin: 0.5em;
}

@media screen and (max-width: 600px) {
  .field-container {
    flex-direction: column;
  }
}
</style>
