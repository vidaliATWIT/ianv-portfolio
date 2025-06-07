<template lang="">
    <div class="wrapper">
        <div class="main-container">
            <div class="title"><h1>Projects:</h1></div>

            <div class="project-card" v-for="(items, index) in projectData.ProjectsArray" v-bind:key="items">
                <h2>{{projectData.ProjectsArray[index].title}}</h2>
                <img :src="projectData.ProjectsArray[index].image" alt="">
                <p>{{projectData.ProjectsArray[index].description}}</p>
                <!--<a href="projectData.ProjectsArray[index].link1">Github</a>-->
            </div>
            <!--{{projectData}}-->
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
</style>
