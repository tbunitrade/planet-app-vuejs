<template>
  <div id="app">
    <PlanetComponent name="Нейминг адрес сайта" :orbitSize="145" :initialTop="50" />
    <PlanetComponent name="Прототипирование проекта" :orbitSize="200" :initialTop="77"/>
    <PlanetComponent name="Дизайн для Веба" :orbitSize="300" :initialTop="250" />
    <PlanetComponent name="Вертска дизайна" :orbitSize="500" :initialTop="750" />
    <PlanetComponent name="Обратная связь" :orbitSize="600" :initialTop="850" />
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
