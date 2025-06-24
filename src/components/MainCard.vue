<template>
    <div class="wrapper">
        <div class="main-container">
            <div class="container1">
                <div class="profile">
                    <img src="../assets/pfp.jpg" alt="">
                    <h3>Ian Vidal</h3>
                    <p>Software Developer</p>
                </div>
                <div class="social-links row">
                    <a class="col col-lg-2" href="https://github.com/vidaliATWIT">
                        <div class="link">
                            <img src="../assets/square-github.svg" alt="">
                            <span class="caption">Github</span>
                        </div>
                    </a>
                    <a class="col col-lg-2" href="https://www.linkedin.com/in/ian-vidal/">
                        <div class="link">
                            <img src="../assets/linkedin.svg" alt="">
                            <span class="caption">LinkedIn</span>
                        </div>
                    </a>
                    <!--<a class="col col-lg-2"  href="">
                        <div class="link">
                            <img src="../assets/square-instagram.svg" alt="">
                            <span class="caption">Instagram</span>
                        </div>
                    </a>-->
                    <a class="col col-lg-2"  href="https://experimentalcolourtransmission.bandcamp.com/">
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
                        <img src="../assets/cplusplus.svg" alt="">
                        <img src="../assets/python.svg" alt="">
                        <img src="../assets/js.svg" alt="">
                        <img src="../assets/golang.svg" alt="">
                        <img src="../assets/html5.svg" alt="">
                        <img src="../assets/css3-alt.svg" alt="">
                        <img src="../assets/vuejs.svg" alt="">
                        <img src="../assets/angular.svg" alt="">
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios';
    export default {
        methods: {
          downloadResume() {
              axios({
                    url: 'http://localhost:8080/resume.pdf', // File URL Goes Here
                    method: 'GET',
                    responseType: 'blob',
                }).then((response) => {
                        const href = URL.createObjectURL(response.data);

                        const link = document.createElement('a');
                        link.href = href;
                        link.setAttribute('download', 'file.pdf');
                        document.body.appendChild(link);
                        link.click();

                        document.body.removeChild(link);
                        URL.revokeObjectURL(href);
                });
          }
      }
    }
</script>

<style scoped>

    .wrapper {
        margin: auto;
        display: flex;
        justify-content: center;
        width: 100%;
    }
    img{
        height: 30px;
    }

    /**
    .social-links {
        display: flex;
        flex-direction: row;
        justify-content: center;
        width: 100%;
    }
    */

   
    /*
    .link {
        vertical-align: top;
        justify-content: center;
        text-align: center;
        display: flex;
        flex-direction: row;
        padding: 20px;
        border: 2px solid black;
    }
    */
    
    .social-links {
        margin: auto;
        display: flex;
        flex-direction: row;
        justify-content: center;
        width: 100%;
    }

    .caption {
        display: block;
        text-align: center;
        color: black;
        width: 20%;
    }

    .link {
        vertical-align: top;
        display: inline-block;
        border: 2px solid rgb(255, 255, 255);
    }

    .link img {
        height: 40px;
    }

    .logos {
        justify-content: center;
    }
    .main-container {
        margin: auto;
        display: flex;
        flex-direction: column;
        background-color: rgb(255, 255, 255);
        width:75%
    }

    .container1 {
        background-color: rgb(255, 255, 255);
        margin: auto;
        padding: .6%;
        height:60%;
        width: 75%
    }

    .container2 {
        background-color: rgb(255, 255, 255);
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
        width: 5%;
    }

    .button-container {
        padding: 2%;
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
    }

    .projects-button {
        background-color: rgb(213, 213, 213); 
        padding: 5px;
        border-radius: 15px;
        margin: 5px;
    }
    .projects-button a{
        text-decoration: none;
        color: black;
    }
    
    
</style>
