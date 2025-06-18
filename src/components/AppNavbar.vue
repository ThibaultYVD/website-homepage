<template>
    <nav class="navbar">
        <div class="navbar-title">
            <h1>Portfolio</h1>
        </div>
        <hr>
        <div class="about-me-container">
            <div class="about-me">
                <div class="profile-container">
                    <img src="../../public/images/me1.png" alt="">
                </div>
                <p id="name">Thibault Yvard</p>

            </div>
            <p class="currently">Currently working at ITGA</p>
        </div>
        <hr>
        <div class="links-container">
            <div class="my-networks">
                <a href="https://github.com">Github<i class="fa-brands fa-github"></i></a>
                <a href="https://linkedin.com">Linkedin<i class="fa-brands fa-linkedin"></i></a>
            </div>

            <div class="cv-container">
                <button>Get my CV</button>
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
a {
    text-decoration: none;
    color: white;
    margin-right: 5px;
}

i {
    font-size: 25px;
}

hr {
    width: 100%;
}

.navbar {
    display: flex;
    flex-direction: column;
    background-color: rgb(17, 16, 63);
    box-shadow: 0px 0px 5px 0px rgba(0, 0, 0, 0.5);
    color: white;
    padding: 1rem;
    width: 15%;
    border-radius: 5px;
    gap: 5px;
}

.navbar-title h1 {
    margin: 0;
    font-size: 1.5rem;
    font-weight: bold;
}

.about-me-container {
    display: flex;
    flex-direction: column;
}

.about-me-container img {
    width: 30px;
    height: 30px;
    align-self: center;
}

.about-me-container #name {
    font-weight: bold;
    font-size: 18px;
}

.about-me {
    display: flex;
    align-items: center;
}

.profile-container {
    width: 30px;
    height: 30px;
    background-color: rgb(112, 208, 181);
    box-shadow: 0px 0px 5px 0px rgba(0, 0, 0, 0.5);
    border-radius: 20px;
    padding: 5px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.currently {
    margin: 0;
    font-size: 12px;
}

.links-container {
    display: flex;
    flex-direction: column;
    gap: 10px;
}

.my-networks {
    display: flex;
    flex-direction: row;
    justify-content: center;
    gap: 5px;
}

.cv-container button {
    width: 100%;
    height: 30px;
}

@media screen and (max-width: 768px) {
    .navbar {
        flex-direction: row;
        align-items: center;
        padding: .5rem
    }

    hr,
    .navbar-title {
        display: none;
    }

    .about-me-container {
        align-items: center;
    }

    .links-container {
        flex-direction: row;
    }
}
</style>