

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

    <div v-for="project in projects">
    <p>{{ project.title }}</p></div>
</template>

<style lang="scss">

</style>