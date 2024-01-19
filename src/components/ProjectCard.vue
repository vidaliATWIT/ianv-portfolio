<template lang="">
    <div class="wrapper">
        <div class="main-container">
            <div class="project-card" v-for="(items, index) in projectData.ProjectsArray" v-bind:key="items">
                <h2>{{projectData.ProjectsArray[index].title}}</h2>
                <img :src="projectData.ProjectsArray[index].image" alt="">
                <p>{{projectData.ProjectsArray[index].description}}</p>
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
    .main-container {
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;
        flex-wrap: wrap;
    }
    .project-card {
        flex-wrap: wrap;
        margin: 10px;
        border: 2px solid black;
    }

    .project-card p {
        margin: auto;
        width: 70%;
        border: 1px solid rgb(255, 255, 255);
        padding: 5px;
    }
    .project-card img {
        height: 20rem;
    }
</style>
