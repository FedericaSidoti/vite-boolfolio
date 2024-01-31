<script>
import axios from "axios";

export default {
    data() {
        return {
            project: null,
            BASE_URL: 'http://127.0.0.1:8000/api'
        };
    },
  methods: {
    fetchProject() {
        axios.get(`${this.BASE_URL}/projects/${this.$route.params.slug}`)
            .then((res) => {
           //console.log(res.data)
                this.project = res.data.project;
                console.log(this.project)
            })
            .catch((error) => {
                console.log("project not found", error.response);

                if (error.response.status === 404) {
                    this.$router.push({ name: "not-found" });
                }
            });
        },
  },
  created() {
    this.fetchProject()
  }
};
</script>

<template>
  <div class="section">
    <div class="container">
      <div class="row">
        <div class="col-6" v-if="project">
            <h1 class="title">{{ project.title }}</h1>
            <img class="img" :src="'http://127.0.0.1:8000'+ project.thumb">
            <p>{{ project.type.name }}</p>
            <p>{{ project.description }}</p>
            <div class="tags" v-if="project.technologies" >
                <p v-for="tech in project.technologies" v-bind:style="{ 'border-color': tech.color }" >{{ tech.name }}</p>
            </div>
        </div>
        <div v-else>Caricamento...</div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" style="scoped">

.col-6 {
    flex-basis: calc((100% / 12)*6);
    display:flex; 
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 12px; 

    .title {
      text-align: center;
    }
}

.img {
    width: 400px; 
}

.tags {
    display: flex;
    flex-wrap: wrap;
    gap: 10px; 
}

.row {
    justify-content: center; 
}

.section {
  margin-bottom: 20px;
  margin-top: 20px;
}

</style>
