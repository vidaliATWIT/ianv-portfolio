<template>
    <div class="wrapper">
        <div class="main-container">
            <div class="container1">
                <div class="profile">
                    <img src="../assets/pfp.jpg" alt="">
                    <h3>Ian Vidal</h3>
                    <p>Software Developer</p>
                </div>
                <div class="social-links">
                    <a href="https://github.com/vidaliATWIT">
                        <div class="link">
                            <img src="../assets/square-github.svg" alt="">
                            <span class="caption">Github</span>
                        </div>
                    </a>
                    <a href="https://www.linkedin.com/in/ian-vidal/">
                        <div class="link">
                            <img src="../assets/linkedin.svg" alt="">
                            <span class="caption">LinkedIn</span>
                        </div>
                    </a>
                    <a href="">
                        <div class="link">
                            <img src="../assets/square-instagram.svg" alt="">
                            <span class="caption">Instagram</span>
                        </div>
                    </a>
                    <a href="https://experimentalcolourtransmission.bandcamp.com/">
                        <div class="link">
                            <img src="../assets/bandcamp.svg" alt="">
                            <span class="caption">Bandcamp</span>
                        </div>
                    </a>
                </div>
            </div>
            <div class="container2">
                <div class="about-me">
                    <h1>About Me</h1>
                    <p>I'm a Software Developer with projects in audio, web development, and game design. 
                        I'm also a musician and published non-fiction writer with articles on musicology and audio tech.
                    </p>
                </div>
                <div class="technology-section">
                    <h3>Tech Stack</h3>
                    <div class="logos">
                        <img src="../assets/python.svg" alt="">
                        <img src="../assets/js.svg" alt="">
                        <img src="../assets/golang.svg" alt="">
                        <img src="../assets/java.svg" alt="">
                        <img src="../assets/html5.svg" alt="">
                        <img src="../assets/css3-alt.svg" alt="">
                        <img src="../assets/vuejs.svg" alt="">
                        <img src="../assets/angular.svg" alt="">
                    </div>
                </div>
                <div class="button-container" >
                    <div class="projects-button">
                        <a href="">My Projects</a>
                    </div>
                    <div class="projects-button">
                        <a href="">My Resume</a>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {

    }
</script>

<style scoped>

    .wrapper {
        display: flex;
        justify-content: center;
    }
    img{
        height: 30px;
    }

    .link {
        vertical-align: top;
        display: inline-block;
        text-align: center;
        width: 120px;
    }
    .social-links img {
        height: 2.5rem
    }
    .caption {
        display: block;
        color: black
    }

    .social-links {
        display: flex;
        flex-direction: row;
        justify-content: center;
    }

    .logos {
        justify-content: center;
    }
    .main-container {
        margin: auto;
        display: flex;
        flex-direction: column;
        background-color: azure;
        width:75%
    }

    .container1 {
        background-color: azure;
        padding: .6%;
        height:60%;
    }

    .container2 {
        background-color: azure;
        padding: .6%;
    }

    .about-me {
        text-align: justified;
        margin: 2.5%;
    }

    .profile img {
        height: 10rem;
        border-radius: 50%;
    }

    .logos img {
        width: 5% 
    }

    .button-container {
        padding: 2%;
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
    }

    .projects-button {
        background-color: blanchedalmond; 
        padding: 5px;
        border-radius: 15px;
        margin: 5px;
    }
    .projects-button a{
        text-decoration: none;
        color: black;
    }
    
    
</style>
