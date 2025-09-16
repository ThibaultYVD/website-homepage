<template>
    <div class="timeline-container">
        <div class="title-container">
            <h1 class="title">Career Timeline</h1>
        </div>
        <div class="timeline-content">
            <div v-for="(item, index) in timelineItems" :key="index" class="timeline-item">
                <div class="timeline-marker"></div>
                <div class="timeline-content-item">
                    <div class="timeline-date">{{ item.date }}</div>
                    <div class="timeline-title">{{ item.title }}</div>
                    <div class="timeline-company">{{ item.company }}</div>
                    <div class="timeline-description">{{ item.description }}</div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "CareerTimeline",
    data() {
        return {
            timelineItems: [
                {
                    date: "2023 - Present",
                    title: "Full Stack Developer",
                    company: "ITGA",
                    description: "Développement d'applications web et mobile, gestion de projets techniques, et collaboration avec les équipes."
                },
                {
                    date: "2022 - 2023",
                    title: "Développeur Web",
                    company: "Freelance",
                    description: "Développement de sites web personnalisés, applications web et solutions techniques pour divers clients."
                },
                {
                    date: "2021 - 2022",
                    title: "Étudiant en Informatique",
                    company: "Formation Autodidacte",
                    description: "Apprentissage intensif des technologies web modernes, frameworks JavaScript, et bonnes pratiques de développement."
                }
            ]
        };
    }
};
</script>

<style scoped>
@import "../assets/styles/components/timeline.css";
</style>
