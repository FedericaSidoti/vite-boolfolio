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

    <div class="card">
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
    flex-wrap: wrap;
    gap: 10px; 
}

</style>