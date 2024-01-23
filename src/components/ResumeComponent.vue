<template>
    <div>
        <div id="app">
            <h2>Download resume</h2>
            <button @click="downloadResume()">Download Resume</button>
        </div>  
    </div>
</template>
<script>
import axios from 'axios';
export default {
    /*
    mounted() {
        'this.downloadResume()'
    },
    */
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
<style>
    
</style>