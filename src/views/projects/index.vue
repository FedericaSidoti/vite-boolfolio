

<script>
    import axios from 'axios';

    export default {
        components: {
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

    <div class="card" v-for="project in projects">
        <h2>{{ project.title }}</h2>
        <p>{{ project.type.name }}</p>
        <p>{{ project.type.description }}</p>
        <div class="tags">
            <p v-for="tech in project.technologies">{{ tech.name }}</p>
        </div>
        
    </div>

</template>

<style lang="scss">

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