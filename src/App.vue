<script>
import ProjectIndex from './views/projects/index.vue';

export default {
    components: {
      ProjectIndex,
    }
  }
</script>

<template>
    <router-view></router-view>
</template>

<style lang="scss">
@use './styles/general.scss';

@import url('https://fonts.googleapis.com/css2?family=Chakra+Petch:wght@300;500;700&family=Dosis:wght@300;500;700&display=swap');
</style>
