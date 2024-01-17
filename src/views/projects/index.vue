

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
                currentPage : 1,
                lastPage: 0,
                page: 0,
                BASE_URL: 'http://127.0.0.1:8000/api'
            }
        },
        methods: {
            fetchProjects() {
                axios.get(`${this.BASE_URL}/projects`, {
                    params: {
                        page: this.page
                    }
                })
                .then((res) => {
                    console.log(res, res.data.results.current_page, res.data.results.last_page)
                    this.projects = res.data.results.data
                    this.currentPage = res.data.results.current_page
                    this.lastPage = res.data.results.last_page
                })
            },
            getPage(n) {

                this.page = n 

                this.fetchProjects()
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
            <div v-if="projects" class="row cards">
                <ProjectCard v-for="project in projects" :project="project" :key="project.id" />
            </div>
            <p v-else> Caricamento...</p>
        </div>
        <div class="section">
            <div class="container">
                <ul class="paginate">
                    <li v-for="n in lastPage">
                        <p :class="n===currentPage? 'active' : ''" @click="getPage(n)">{{ n }}</p>
                    </li>
                </ul>
            </div>
        </div>
    </div>
    

    

</template>

<style lang="scss">

.section {
    padding: 30px; 
}

.paginate {
    display:flex; 
    justify-content: center; 
    gap: 10px; 
    
    p {
        text-align: center; 
        cursor: pointer;
    }
}

.active {
    color: #FEC572; 
    font-size: bold; 
}

.cards {
    padding: 10px 20px; 

}


</style>