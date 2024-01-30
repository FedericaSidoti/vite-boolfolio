<script>

    export default {
        components: {
        },
        data() {
            return {
                
            }
        },
        methods: {
            
        },
        props: {
            project: {
                type: Object,
                required: true
            }
        },
        created() {
        }
    }
</script>

<template>
    
    <div class="col-3">
        <div class="card">
            <h2>{{ project.title }}</h2>
            <img v-if="project.thumb" class="thumb" :src="'http://127.0.0.1:8000' + project.thumb">
            <p>{{ project.type.name }}</p>
            <p>{{ project.type.description }}</p>
            <div class="tags">
                <p v-for="tech in project.technologies" v-bind:style="{ 'border-color': tech.color } ">{{ tech.name }} </p>
            </div>
            <p class="link">
                <router-link :to="{ name: 'projects.show', params: { slug: project.slug }}">Dettagli</router-link>
            </p>
        </div>
    </div>
    

</template>

<style lang="scss">

.col-3{
    padding: 10px; 
}

.card {
    display: flex; 
    flex-direction:column; 
    justify-content: center;
    align-items: center;
    gap: 10px; 
    padding: 10px; 
    height: 100%;
    border-radius: 10px; 

    &:hover {
        border: 3px solid  #FEC572;
    }

    h2{
        color : #1C506E;
        text-align: center;
    }

    .thumb {
        max-width: 100%; 
    }

    .link {
        text-align: center;
        margin-top: auto;
        font-size: 18px; 
        font-weight: 700;
        color: #FEC572;
        background-color: #1C506E;
        border-radius: 10px;
        padding: 2px 8px; 
        width: 60%;
    }
}

.tags {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 3px; 
        p {
            border-radius : 10px; 
            padding: 2px 8px ; 
            border: 2px solid; 
        }
}

</style>