<template>
    <nav class="navbar">
        <div class="navbar-title">
            <h1>Portfolio</h1>
        </div>
        <hr>
        <div class="about-me-container">
            <div class="about-me">
                <div class="profile-container">
                    <img src="../../public/images/me.png" alt="">
                </div>
                <p>Thibault Yvard</p>
            </div>
            <div class="my-networks">
                <a href="github.com"><i class="fa-brands fa-github"></i></a>
                <a href="github.com"><i class="fa-brands fa-linkedin"></i></a>
            </div>
        </div>
        <hr>
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
    width: 10%;
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

.about-me-container p {
    font-weight: bold;
    font-size: 18px;
}

.about-me{
    display: flex;
    align-items: center;
}

.profile-container {
    width: 30px;
    height: 30px;
    background-color: black;
    box-shadow: 0px 0px 5px 0px rgba(0, 0, 0, 0.5);
    border-radius: 20px;
    padding: 5px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.my-networks {
    display: flex;
    flex-direction: row;
    justify-content: center;
    gap: 5px;
}
</style>