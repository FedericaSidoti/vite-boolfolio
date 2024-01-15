

<script>
    import ProjectCard from '../../components/ProjectCard.vue';
    import axios from 'axios';

    export default {
        components: {
            ProjectCard,
        },
        data() {
            return {
                projects: [],
                BASE_URL: 'http://127.0.0.1:8000/api'
            }
        },
        methods: {
            fetchProjects() {
                axios.get(`${this.BASE_URL}/projects`)
                .then((res) => {
                    console.log(res)
                    this.projects = res.data.results
                })
            }
        },
        created() {
            this.fetchProjects()
        }
    }
</script>

<template>
    <div class="section">
        <div class="container">
            <div class="row">
                <ProjectCard class="col-3" v-for="project in projects" :project="project" :key="project.id" />
            </div>
        </div>
    </div>
    

    

</template>

<style lang="scss">

.section {
    padding: 30px; 
}

.card {
    display: flex; 
    border: 1px solid black;
    flex-direction:column; 
    gap: 10px; 
    padding: 10px; 
}

.tags {
    display: flex;
    gap: 10px; 
}

</style>