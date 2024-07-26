<template>
  <div id="app">
    <div class="sun"></div>
    <PlanetComponent name="Нейминг адрес сайта" :orbitSize="500" :initialTop="250" :orbitSpeed="10" />
    <PlanetComponent name="Прототипирование проекта" :orbitSize="500" :initialTop="277" :orbitSpeed="15"/>
    <PlanetComponent name="Дизайн для Веба" :orbitSize="500" :initialTop="450" :orbitSpeed="50"/>
    <PlanetComponent name="Вертска дизайна" :orbitSize="500" :initialTop="500" :orbitSpeed="25" />
    <PlanetComponent name="Обратная связь" :orbitSize="500" :initialTop="550"  :orbitSpeed="300"/>
  </div>
</template>

<script>
import PlanetComponent from './components/PlanetComponent.vue';

export default {
  components: {
    PlanetComponent
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
