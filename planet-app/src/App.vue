<template>
  <div id="app">
    <SunComponent @expand="handleSunExpand" />
    <PlanetsComponent :isExpanding="isExpanding" />
  </div>
</template>

<script>
import SunComponent from './components/Sun/SunComponent.vue';
import PlanetsComponent from './components/Planets/PlanetsComponent.vue';

export default {
  components: {
    SunComponent,
    PlanetsComponent
  },
  data() {
    return {
      isExpanding: false
    };
  },
  methods: {
    handleSunExpand() {
      this.isExpanding = true;
    }
  }
};
</script>

<style>
#app {
  position: relative;
  width: 100vw;
  height: 100vh;
  background-color: #000;
  overflow: hidden;
}
</style>
