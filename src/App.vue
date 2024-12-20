<template>
  <div id="app">
    <AppNavbar />
    <div class="main-container">
      <div class="top">
        Hi and welcome on my website! You can find here my projects and the services hosted on this
        server. If you want to learn more about me and my projects, please take a look at my Linkedin and my Github
        accounts.
      </div>
      <div class="center-container">
        <div class="projects-container">
          <h1>Projects</h1>
          <p>
            Thoses projects are developed by me and run on this server. You can try them if you want!
          </p>
          <QuicklinksList :items="projects" />
        </div>
        <div class="quicklinks-container">
          <h1>Services</h1>
          <p>Those services are hosted on my server. Only verified people can use them.</p>
          <QuicklinksList :items="quicklinks" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import AppNavbar from "./components/AppNavbar.vue";
import QuicklinksList from "./components/List.vue";

// Importation du JSON local
import data from "@/assets/data.json";

export default {
  name: "App",
  components: {
    AppNavbar,
    QuicklinksList,
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
body {
  margin: 0px;
  padding: 0px;
}

#app {
  display: flex;
  flex-direction: column;
}

.main-container {
  display: flex;
  flex-direction: column;
  padding-top: 50px;
  padding-left: 200px;
  padding-right: 200px;
  gap: 50px;
}

.center-container {
  display: flex;
  gap: 30px;
}

.projects-container,
.quicklinks-container {
  width: 50%;
  border-radius: 10px;
  box-shadow: 0px 0px 10px 0px rgba(0, 0, 0, 0.75);
  padding: 20px;
}
</style>
