<template>
    <div class="wrapper">
        <div class="main-container">
            <div class="title"><h1>Projects:</h1></div>
            <div class="project-card" v-for="project in projectData.ProjectsArray" :key="project.id">
                <h2>{{ project.title }}</h2>
                
                <!-- Conditional YouTube embed or image -->
                <div class="media-container">
                    <iframe 
                        v-if="project['video-link']"
                        :src="getYouTubeEmbedUrl(project['video-link'])"
                        width="560" 
                        height="315" 
                        frameborder="0" 
                        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
                        allowfullscreen>
                    </iframe>
                    <img 
                        v-else
                        :src="project.image" 
                        :alt="project.title">
                </div>
                
                <p>{{ project.description }}</p>

                <div class="project-links" v-if="project['link-1']">
                    <a v-if="project['link-1']" :href="project['link-1']" target="_blank">[GitHub]</a>
                </div>
                <div class="project-links" v-if="project['link-2']">
                    <a v-if="project['link-2']" :href="project['link-2']" target="_blank">[{{project['link-2-name']}}]</a>
                </div>

            </div>
            <div class="button-container" >
                <div class="projects-button">
                    <a href="https://ian-v-portfolio.web.app/resume.pdf" target="__blank" rel="noopener noreferrer">My Resume (PDF)</a>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import jsonData from "/projects.json"

export default {
    data(){
        return{
            projectData: jsonData
        }
    },
    methods: {
        getYouTubeEmbedUrl(url) {
            // Extract video ID from YouTube URL
            const videoId = this.extractYouTubeId(url);
            return `https://www.youtube.com/embed/${videoId}`;
        },
        
        extractYouTubeId(url) {
            // Handle different YouTube URL formats
            const regExp = /^.*(youtu.be\/|v\/|u\/\w\/|embed\/|watch\?v=|&v=)([^#&?]*).*/;
            const match = url.match(regExp);
            return (match && match[2].length === 11) ? match[2] : null;
        }
    }
}
</script>

<style>
    .wrapper {
        margin: auto;
        display: flex;
        justify-content: center;
        width: 100%;
    }
    .main-container {
        padding: 0.0%;
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;
        flex-wrap: wrap;
        max-width: 75%;
        flex: 1 1 0;
    }

    .title {
        text-decoration: bold;
    }
    .project-card {
        flex-wrap: wrap;
        margin: 10px;
        /*border: 1px solid rgb(0, 0, 0);*/
        width: 100%;
        padding: 1.0%;
    }

    .project-card p {
        margin: auto;
        width: 75%;
        border: 1px solid rgb(255, 255, 255);
        padding: 5px;
    }
    .project-card img {
        height: auto;
        max-width: 60%;
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
    .media-container {
        width: 100%;
        max-width: 560px;
        margin: 0 auto;
    }

    .media-container iframe {
        width: 100%;
        height: auto;
        aspect-ratio: 16/9;
    }

    .media-container img {
        width: 100%;
        height: auto;
        max-width: 560px;
    }

</style>
