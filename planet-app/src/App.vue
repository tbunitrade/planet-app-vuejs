<template>
  <div id="app">
    <Planet name="Нейминг адрес сайта" :orbitSize="145" />
    <Planet name="Прототипирование проекта" :orbitSize="200" />
    <Planet name="Дизайн для Веба"  :orbitSize="300" />
    <Planet name="Вертска дизайна" :orbitSize="500"/>
    <Planet name="Обратная связь" :orbitSize="600" />
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



@media (max-width: 600px) {
.planet {
width: 50px;
height: 50px;
}
}

.planet {
  animation: rotate 10s linear infinite;
}

@keyframes rotate {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}


</style>
