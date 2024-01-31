<script>
import ProjectCard from "../../components/ProjectCard.vue";
import axios from "axios";

export default {
components: {
    ProjectCard,
},
data() {
    return {
    projects: [],
    currentPage: 1,
    lastPage: 0,
    page: 0,
    BASE_URL: "http://127.0.0.1:8000/api",
    };
},
methods: {
    fetchProjects() {
    axios
        .get(`${this.BASE_URL}/projects`, {
        params: {
            page: this.page,
        },
        })
        .then((res) => {
        console.log(
            res,
            res.data.results.current_page,
            res.data.results.last_page
        );
        this.projects = res.data.results.data;
        this.currentPage = res.data.results.current_page;
        this.lastPage = res.data.results.last_page;
        });
    },
    getPage(n) {
    this.page = n;

    this.fetchProjects();
    } ,
},
beforeMount() {
    this.fetchProjects();
},
};
</script>

<template>
    <div class="section">
    <div class="container">
        <div v-if="projects.length > 0" class="row cards">
        <ProjectCard
            class="card_"
            v-for="project in projects"
            :project="project"
            :key="project.id"
        />
        </div>
        <div class="loading" v-else>
            <p>Caricamento...</p>
            <img src="/img/loading.webp">
        </div>
    </div>
    <div class="section">
        <div class="container">
        <ul class="paginate">
            <li v-for="n in lastPage">
            <p :class="n === currentPage ? 'active' : ''" @click="getPage(n)">
                {{ n }}
            </p>
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
  display: flex;
  justify-content: center;
  gap: 10px;

  li {
    border: 2px solid #3b7ed6;
    border-radius: 10px;
    padding: 2px 8px; 
    background-color: rgb(173, 209, 232);
  }

  p {
    text-align: center;
    cursor: pointer;
  }
}

.active {
  color: #3b7ed6;
  font-weight: bold;
}

.cards {
  padding: 10px 20px;
}

.card_:hover {
  transform: scale(1.1);
}

.loading {
    padding: 50px; 
    display: flex;
    flex-direction: column;
    margin: 0 auto; 
    justify-content: center;
    align-items: center;

    p {
        font-size: 30px; 
    }

    img {
        height: 200px; 
    }

}
</style>
