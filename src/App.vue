<template>
  <div id="app">
    <AppNavbar />
    <div class="main-container">
      <div class="top-container">
        Hi and welcome on my website! Here you can find my projects and the services hosted on this
        server. If you want to learn more about me and my projects, please take a look at my Linkedin and my Github
        accounts.
      </div>
      <div class="center-container">
        <div class="projects-container">
          <h1>Projects</h1>
          <p>
            Those projects are developed by me and run on this server. You can try them if you want!
          </p>
          <AppList :items="projects" />
        </div>
        <div class="quicklinks-container">
          <h1>Services</h1>
          <p>Those services are hosted on my server. Only verified people can use them.</p>
          <AppList :items="quicklinks" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import AppNavbar from "./components/AppNavbar.vue";
import AppList from "./components/AppList.vue";

// Importation du JSON local
import data from "@/assets/data.json";

export default {
  name: "App",
  components: {
    AppNavbar,
    AppList,
  },
  data() {
    return {
      projects: data.projects,
      quicklinks: data.quicklinks, // Récupère la partie quicklinks

    };
  },
};
</script>

<style>
html,
body {
  margin: 0px;
  padding: 0px;
  font-family: sans-serif;
  height: 99%;
  padding: 4px;
  background: linear-gradient(to bottom right, #dceeff, #8abce6);

}

#app {
  display: flex;
  flex-direction: row;
  min-height: 100%;
}

.main-container {
  display: flex;
  flex-direction: column;
  padding: 4px 50px;
  gap: 50px;
  width: 90%;
}

.top-container {
  padding: 25px;
  border-radius: 10px;
}

.center-container {
  display: flex;
  gap: 30px;
}

.projects-container,
.quicklinks-container {
  width: 50%;
  border-radius: 10px;
  background-color: rgb(255, 255, 255);
  box-shadow: 0px 3px 5px 0px rgba(0, 0, 0, 0.3);
  padding: 0 20px 20px 20px;
}
</style>