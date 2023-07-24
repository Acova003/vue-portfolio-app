<template>
  <div>
    <!-- Button that sets isAdmin to true -->
    <div class="buttons-container">
      <nav>
        <button
          :class="{ 'button is-danger': isAdmin, 'button is-light': !isAdmin }"
          @click="isAdmin = true"
        >
          ADMIN
        </button>
        <!-- Button that sets isAdmin to false -->
        <button
          :class="{ 'button is-danger': !isAdmin, 'button is-light': isAdmin }"
          @click="isAdmin = false"
        >
          USER
        </button>
      </nav>
    </div>

    <!-- Header Hello World -->
    <h1 id="headline">My Portfolio</h1>

    <!-- If isAdmin is true, show adminView, else show userView -->
    <admin-view v-if="isAdmin" @createProject="addProject" />
    <user-view v-else :projects="allProjects" />
  </div>
</template>

<script>
// Importing components from the components folder
import AdminView from "./components/AdminView.vue";
import UserView from "./components/UserView.vue";

// Exporting the App component
export default {
  // Name of the component
  name: "app",
  // Components that are used inside the App component
  components: {
    // Key: Value
    userView: UserView,
    adminView: AdminView,
  },
  // Data that is used inside the App component
  data() {
    // Return the data
    return {
      // isAdmin is a boolean that is used to determine which view to show
      isAdmin: true,
      // allProjects is an array that is used to store all the projects
      allProjects: new Array(8).fill(null).map((e, i) => ({
        title: `My project number ${i + 1}`,
        image: `https://picsum.photos/seed/${Math.random()}/600/400`,
        description: "Lorem ipsum dolo",
      })),
    };
  },
  // Methods that are used inside the App component
  methods: {
    addProject(newProject) {
      const regEx =
        /^https?:\/\/(?:www\.)?[-a-zA-Z0-9@:%._\+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_\+.~#?&//=]*)$/gm;

      if (
        newProject.title !== "" &&
        newProject.image !== "" &&
        newProject.image.match(regEx) &&
        newProject.description !== ""
      ) {
        this.allProjects.push(newProject);
      }
    },
  },
};
</script>

<!-- Styling for components -->
<style>
.buttons-container {
  display: flex;
  justify-content: flex-end;
  margin-top: 20px;
  margin-bottom: 20px;
  padding-right: 20px;
}

#headline {
  text-align: center;
  font-size: 50px;
  font-family: sans-serif;
}
</style>
