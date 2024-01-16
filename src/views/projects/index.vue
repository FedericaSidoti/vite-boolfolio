

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
    
    <header>
        <div class="container-fluid navbar">
            <ul class="links">
                <li>
                    logo
                </li>
                <li>
                    <p>MyProjects</p>
                </li>
            </ul>
            <ul class="links">
                <li>Home</li>
                <li>Admin</li>
            </ul>
        </div>
    </header>

    <div class="section">
        <div class="container">
            <div class="row cards">
                <ProjectCard v-for="project in projects" :project="project" :key="project.id" />
            </div>
        </div>
    </div>
    

    

</template>

<style lang="scss">

.section {
    padding: 30px; 
}

.navbar {
    display: flex; 
    justify-content: space-around;
    padding: 10px 0; 
    background-color: #1C506E;
    color:  #F18908;

    .links {
        display: flex; 
        gap: 10px; 

        li:hover {
            color: #FEC572;
        }
    }
}

.cards {
    padding: 10px 20px; 

}


</style>