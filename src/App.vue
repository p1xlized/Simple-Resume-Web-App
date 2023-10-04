<template>
  <nav>
    <router-link to="/" class="nav-link" exact-active-class="active-link">Home</router-link>
    <router-link to="/music" class="nav-link" exact-active-class="active-link">Music Projects</router-link>
    <router-link to="/projects" class="nav-link" exact-active-class="active-link">IT Projects</router-link>

    <!-- Container for the buttons -->
    <div class="nav-buttons-container">
      <!-- GitHub button -->
      <a href="https://github.com/your-github-username" target="_blank" class="nav-button">Source Code</a>

      <router-link to="/links" class="nav-button" exact-active-class="active-link" @click="toggleModal">Links</router-link>
    </div>
  </nav>
  <div class="app">
    <router-view/>
  <ModalComponent v-if="showModal" @close="toggleModal" />
  </div>
  
  <footer>
    <p>&copy; 2023 Alex Paduret</p>
  </footer>
</template>

<script>
import ModalComponent from "./components/ModalComponent.vue";
export default {
  name: "App",
  components: { ModalComponent },
  data() {
    return {
      showModal: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    }
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #cdd6f4;
}


nav {
  background-color: #1e1e2e;
  padding: 15px;
  border-radius: 10px;
  display: flex;
  justify-content: space-between; /* Separate content and buttons */
  align-items: center;
}

.nav-link {
  font-weight: bold;
  color: #a6adc8;
  text-decoration: none;
  margin-right: 15px;
  display: flex;
  align-items: center;
}

.nav-buttons-container {
  display: flex;
  margin-left: auto; /* Align the buttons to the right */
  margin-right: 10px; /* Add margin between the buttons */
}

.nav-button {
  font-weight: bold;
  color: #fff;
  text-decoration: none;
  background-color: #eba0ac;
  padding: 5px 5px;
  border-radius: 5px;
  margin-right: 5px; /* Add margin between the buttons */
}

/* Add space between "Home" and buttons */
nav :first-child {
  margin-right: 20px;
}

/* Style for the active link */
.active-link {
  color: #eba0ac; /* Set active link color to red */
}

.nav-button:hover {
  background-color: #ff6b81;
}
</style>
