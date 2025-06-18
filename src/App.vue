<template>
  <div id="app">
    <AppNavbar />
    <div class="main-container">
      <div class="top-container">
        Welcome on my website! Here you can find my projects and the services hosted on this
        server. If you want to learn more about me and my projects, please take a look at my Linkedin and my Github
        accounts.
      </div>
      <div class="center-container">
        <div class="projects-container">
          <h1 class="title">Projects</h1>
          <AppList :items="projects" />
        </div>
        <div class="quicklinks-container">
          <h1 class="title">Services</h1>
          <AppList :items="quicklinks" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import AppNavbar from "./components/AppNavbar.vue";
import AppList from "./components/AppList.vue";

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
  background: #e8e8e8;

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

.title {
  border-bottom: 4px rgba(0, 0, 0, 0.8) solid;
  border-radius: 4px;
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

@media screen and (max-width: 768px) {
  #app {
    flex-direction: column;
  }

  .center-container {
    flex-direction: column-reverse;
    padding: 0;
    margin: 0;
  }

  .projects-container,
  .quicklinks-container {
    width: 100%;
  }

  .main-container {
    width: 100%;
    padding: 0;
  }

  .center-container div {
    width: 100%;
  }
}
</style>