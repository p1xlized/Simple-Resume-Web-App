<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{ dark: theme === 'dark' }">
      <h1>LINK TREE</h1>
      <ul>
        <li><a href="https://soundcloud.com/your-soundcloud" target="_blank">SoundCloud</a></li>
        <li><a href="https://discord.gg/your-discord" target="_blank">Discord</a></li>
        <li><a href="https://www.reddit.com/user/your-reddit" target="_blank">Reddit</a></li>
        <li><a href="https://twitter.com/your-twitter" target="_blank">Twitter</a></li>
        <li><a href="https://www.linkedin.com/in/your-linkedin" target="_blank">LinkedIn</a></li>
        <li><a href="https://gitlab.com/your-gitlab" target="_blank">GitLab</a></li>
        <li><a href="https://github.com/your-github" target="_blank">GitHub</a></li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>

<style>
.modal {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: #45475a;
  border-radius: 10px;
}
.backdrop {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}
.modal h1 {
  font-style: bold;
  color: #cdd6f4;
  border: none;
  padding: 0;
}
.modal.dark {
  background: darkgray;
  color: white;
}
.modal.dark h1 {
  color: white;
}
ul {
  list-style: none;
  padding: 0;
}
li {
  margin-bottom: 10px;
}
a {
  text-decoration: none;
  color: #333; /* Link color */
  font-weight: bold;
}
a:hover {
  color: #eb4034; /* Hover color */
}
</style>
