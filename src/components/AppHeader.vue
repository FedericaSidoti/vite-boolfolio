<script>

export default {
    data() {
        return {

        }
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
                    <router-link :to="{name:'home'}">Home</router-link>
                </li>
            </ul>
            <ul class="links">
                <li>
                    <router-link :to="{name:'contacts'}">Contatti</router-link>
                </li>
                <li>
                    <router-link :to="{name:'projects.index'}">Portfolio</router-link>
                </li>
            </ul>
        </div>
    </header>

</template>

<style lang="scss">
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
</style>