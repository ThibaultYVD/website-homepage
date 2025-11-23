<template>
    <nav class="navbar">
        <div class="navbar-section">
            <div class="navbar-title">
                <h1>Portfolio</h1>
            </div>
        </div>

        <div class="navbar-section profile-section">
            <div class="about-me-container">
                <div class="about-me">
                    <div class="profile-container">
                        <img src="../../public/images/me1.png" alt="Profile picture">
                    </div>
                    <div class="profile-info">
                        <p id="name">Thibault Yvard</p>
                        <p class="currently">Currently working at ITGA</p>
                    </div>
                </div>
            </div>
        </div>

        <div class="navbar-section">
            <div class="links-container">
                <div class="section-title">Connect with me</div>
                <div class="my-networks">
                    <a href="https://github.com/ThibaultYVD" class="network-link">
                        <i class="fa-brands fa-github"></i>
                        <span>Github</span>
                    </a>
                    <a href="https://www.linkedin.com/in/thibault-yvard/" class="network-link">
                        <i class="fa-brands fa-linkedin"></i>
                        <span>Linkedin</span>
                    </a>
                    <a href="https://www.linkedin.com/in/thibault-yvard/" class="network-link">
                        <i class="fa-solid fa-envelope"></i>
                        <span>contact@thibault-yvard.fr</span>
                    </a>
                </div>
            </div>
        </div>

        <div class="navbar-section">
            <div class="cv-container">
                <a href="https://nextcloud.thibault-yvard.fr/s/TB6X2g9J3MKaAdq" target="_blank" class="cv-button">
                    <i class="fa-solid fa-download"></i>
                    Get my CV
                </a>
            </div>
        </div>
    </nav>
</template>

<script>
export default {
    name: "AppNavbar",
};
</script>
<style scoped>
@import "../assets/styles/components/navbar.css";
</style>