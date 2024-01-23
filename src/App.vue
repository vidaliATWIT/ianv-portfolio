<template>
  <div id="app">
    <MainCard/>
    <ProjectCard/>
  </div>
</template>

<script>
import MainCard from './components/MainCard.vue';
import ProjectCard from './components/ProjectCard.vue';
//import NavCard from './components/NavCard.vue';
export default {
  name: 'App',
  components: {
    MainCard,
    ProjectCard,
    //NavCard,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  align-content: center;
}
</style>
