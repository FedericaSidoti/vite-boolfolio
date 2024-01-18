<script>
import AppHeader from './components/AppHeader.vue';

export default {
    components: {
      AppHeader,
    }
  }
</script>

<template>
    <AppHeader/>
    <router-view></router-view>
</template>

<style lang="scss">
@use './styles/general.scss';

@import url('https://fonts.googleapis.com/css2?family=Chakra+Petch:wght@300;500;700&family=Dosis:wght@300;500;700&display=swap');
</style>
