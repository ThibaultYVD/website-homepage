<template>
  <div class="main-wrapper">
    <div id="app">
      <AppNavbar />
      <div class="main-container">
        <div class="top-container">
          Welcome on my website! Here you can find my projects and the services hosted on
          this server. If you want to learn more about me and my projects, please take a
          look at my Github and Linkedin accounts.
        </div>
        <div class="center-container">
          <div class="projects-container">
            <div class="title-container">
              <h1 class="title">Projects</h1>
            </div>
            <div class="list-scroll-container">
              <AppList :items="projects" />
            </div>
          </div>
          <div class="quicklinks-container">
            <div class="title-container">
              <h1 class="title">Services</h1>
            </div>
            <div class="list-scroll-container">
              <AppList :items="quicklinks" />
            </div>
          </div>
        </div>
        <div class="timeline-section">
          <CareerTimeline />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import AppNavbar from "./components/AppNavbar.vue";
import AppList from "./components/AppList.vue";
import CareerTimeline from "./components/CareerTimeline.vue";

import data from "@/assets/data.json";

export default {
  name: "App",
  components: {
    AppNavbar,
    AppList,
    CareerTimeline,
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
/* App-specific styles only */
.projects-container,
.quicklinks-container {
  display: flex;
  flex-direction: column;
  background: var(--card-background);
  border-radius: var(--border-radius);
  box-shadow: var(--shadow-md);
  border: 1px solid rgba(0, 0, 0, 0.05);
  overflow: hidden;
}

.timeline-section {
  margin-top: var(--spacing-lg);
  height: 400px;
}

.list-scroll-container {
  padding: 0 var(--spacing-lg) var(--spacing-lg);
  overflow-y: auto;
  height: 100%;
}

.title-container {
  position: sticky;
  top: 0;
  background: var(--card-background);
  padding: var(--spacing-lg) var(--spacing-lg) 0;
  margin-bottom: var(--spacing-md);
  z-index: 10;
}

.title {
  font-size: 1.5rem;
  font-weight: 600;
  margin: 0;
  padding-bottom: var(--spacing-sm);
  border-bottom: 3px solid var(--primary-color);
  color: var(--primary-color);
}

@media screen and (max-width: 768px) {

  .projects-container,
  .quicklinks-container {
    max-height: 500px;
  }

  .title {
    font-size: 1.25rem;
  }
}

@media screen and (max-width: 480px) {

  .projects-container,
  .quicklinks-container {
    max-height: 400px;
  }
}

:root {
  --primary-color: rgb(17, 16, 63);
  --accent-color: rgb(41, 98, 255);
  --background-color: #f5f5f5;
  --text-color: #333;
  --card-background: #fff;
  --shadow-sm: 0 2px 4px rgba(0, 0, 0, 0.1);
  --shadow-md: 0 4px 6px rgba(0, 0, 0, 0.1);
  --shadow-lg: 0 8px 16px rgba(0, 0, 0, 0.1);
  --spacing-xs: 0.25rem;
  --spacing-sm: 0.5rem;
  --spacing-md: 1rem;
  --spacing-lg: 1.5rem;
  --spacing-xl: 2rem;
  --border-radius: 12px;
  --border-radius-sm: 8px;
  --max-width: 1400px;
  --header-height: 90px;
  --list-max-height: calc(100vh - var(--header-height) - 12rem);
}

/* Scrollbar personnalisée */
::-webkit-scrollbar {
  width: 8px;
  height: 8px;
}

::-webkit-scrollbar-track {
  background: rgba(0, 0, 0, 0.05);
  border-radius: 4px;
}

::-webkit-scrollbar-thumb {
  background: rgba(0, 0, 0, 0.2);
  border-radius: 4px;
  transition: background 0.2s ease;
}

::-webkit-scrollbar-thumb:hover {
  background: rgba(0, 0, 0, 0.3);
}

html,
body {
  margin: 0;
  padding: 0;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  background: var(--background-color);
  color: var(--text-color);
  line-height: 1.6;
  min-height: 100vh;
  overflow: hidden;
}

#app {
  display: flex;
  min-height: calc(100vh - var(--spacing-md) * 2);
  /* Hauteur minimale en tenant compte du padding */
  max-width: var(--max-width);
  margin: 0 auto;
  padding: var(--spacing-md);
  gap: var(--spacing-xl);
  overflow: hidden;
}

/* Wrapper pour centrer le contenu verticalement */
.main-wrapper {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

body {
  margin: 0;
  padding: 0;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  background: var(--background-color);
  color: var(--text-color);
  line-height: 1.6;
  height: 100vh;
  overflow: hidden;
}

#app {
  display: flex;
  height: calc(100vh - var(--spacing-md) * 2);
  /* Soustrait le padding haut et bas */
  max-width: var(--max-width);
  margin: 0 auto;
  padding: var(--spacing-md);
  gap: var(--spacing-xl);
  overflow: hidden;
}

.main-container {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: var(--spacing-lg);
  overflow: hidden;
  min-width: 0;
  max-height: calc(100vh - var(--header-height) - var(--spacing-md) * 2);
  height: 100%;
}

.top-container {
  background: var(--card-background);
  padding: var(--spacing-lg);
  border-radius: var(--border-radius);
  box-shadow: var(--shadow-md);
  font-size: 1.1rem;
  line-height: 1.8;
  border: 1px solid rgba(0, 0, 0, 0.05);
}

.center-container {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: var(--spacing-xl);
  min-height: 0;
  /* Pour permettre aux enfants de scroll */
  flex: 1;
}

.projects-container,
.quicklinks-container {
  display: flex;
  flex-direction: column;
  background: var(--card-background);
  border-radius: var(--border-radius);
  box-shadow: var(--shadow-md);
  border: 1px solid rgba(0, 0, 0, 0.05);
  overflow: hidden;
  /* Pour contenir la scrollbar */
}

.list-scroll-container {
  padding: 0 var(--spacing-lg) var(--spacing-lg);
  overflow-y: auto;
  height: 100%;
}

.title-container {
  position: sticky;
  top: 0;
  background: var(--card-background);
  padding: var(--spacing-lg) var(--spacing-lg) 0;
  margin-bottom: var(--spacing-md);
  z-index: 10;
}

.title {
  font-size: 1.5rem;
  font-weight: 600;
  margin: 0;
  padding-bottom: var(--spacing-sm);
  border-bottom: 3px solid var(--primary-color);
  color: var(--primary-color);
}

/* Tablette */
@media screen and (max-width: 1024px) {
  :root {
    --spacing-xl: 1.5rem;
    --spacing-lg: 1rem;
  }

  #app {
    padding: var(--spacing-md);
  }

  .center-container {
    grid-template-columns: 1fr;
    gap: var(--spacing-lg);
  }
}

/* Mobile */
@media screen and (max-width: 768px) {

  html,
  body {
    height: auto;
    overflow: auto;
  }

  .main-wrapper {
    padding: var(--spacing-sm);
    min-height: auto;
  }

  #app {
    flex-direction: column;
    height: auto;
    min-height: auto;
    padding: 0;
    overflow: auto;
  }

  .main-container {
    gap: var(--spacing-md);
  }

  .center-container {
    grid-template-columns: 1fr;
    gap: var(--spacing-md);
  }

  .top-container {
    padding: var(--spacing-lg);
    font-size: 1rem;
  }

  .projects-container,
  .quicklinks-container {
    max-height: 500px;
    /* Hauteur fixe sur mobile */
  }

  .title {
    font-size: 1.25rem;
  }

  .list-scroll-container {
    padding: 0 var(--spacing-md) var(--spacing-md);
  }

  .timeline-section {
    height: 350px;
    margin-top: var(--spacing-md);
  }
}

/* Petit Mobile */
@media screen and (max-width: 480px) {
  .top-container {
    padding: var(--spacing-md);
  }

  .projects-container,
  .quicklinks-container {
    max-height: 400px;
  }

  .list-scroll-container {
    padding: 0 var(--spacing-sm) var(--spacing-sm);
  }

  .timeline-section {
    height: 300px;
    margin-top: var(--spacing-sm);
  }
}
</style>
