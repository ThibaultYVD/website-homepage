<template>
    <nav class="navbar">
        <div class="navbar-brand">
            <h1>Thibault's server homepage</h1>
        </div>
    </nav>
</template>

<script>
export default {
    name: "AppNavbar", // Nom multi-word du composant
};
</script>

<style scoped>
.navbar {
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #2c3e50;
    color: white;
    padding: 1rem;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.navbar-brand h1 {
    margin: 0;
    font-size: 1.5rem;
    font-weight: bold;
}
</style>