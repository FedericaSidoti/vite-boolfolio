<script>
import AppHeader from './components/AppHeader.vue';

export default {
    components: {
      AppHeader,
    }
  }
</script>

<template>
    <AppHeader />
      <router-view class="main" v-slot="{ Component }">
        <transition name="slide">
          <component :is="Component" />
        </transition>
      </router-view>

</template>

<style lang="scss">
@use './styles/general.scss';

.slide-enter-active,
.slide-leave-active {
  transition: all 0.3s ease-out;
}

.slide-enter-to {
  position: absolute;
  right: 0;
}

.slide-enter-from {
  position: absolute;
  right: -100%;
}

.slide-leave-to {
  position: absolute;
  left: -100%;
}

.slide-leave-from {
  position: absolute;
  left: 0;
}

.main {
  padding: 50px; 
  min-height: 100vh;
}


@import url('https://fonts.googleapis.com/css2?family=Chakra+Petch:wght@300;500;700&family=Dosis:wght@300;500;700&display=swap');
</style>
