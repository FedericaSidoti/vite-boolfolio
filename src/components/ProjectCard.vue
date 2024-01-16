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
            <img class="thumb" :src="project.thumb">
            <p>{{ project.type.name }}</p>
            <p>{{ project.type.description }}</p>
            <div class="tags">
                <p v-for="tech in project.technologies">{{ tech.name }}</p>
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
    gap: 10px; 
    padding: 10px; 
    height: 100%;
    border-radius: 10px; 

    &:hover {
        border: 3px solid  #FEC572;
    }

    h2{
        color : #1C506E;
    }

    .thumb {
        max-width: 100%; 
    }

    .link {
        font-size: 22px; 
        font-weight: 700;
    }
}

.tags {
    display: flex;
    flex-wrap: wrap;
    gap: 10px; 
}

</style>