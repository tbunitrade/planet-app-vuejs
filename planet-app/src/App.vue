<template>
  <div id="app">
    <Planet name="Нейминг адрес сайта" />
    <Planet name="Прототипирование проекта" />
    <Planet name="Дизайн для Веба" />
    <Planet name="Вертска дизайна" />
    <Planet name="Обратная связь" />
  </div>
</template>

<script>
import Planet from './components/PlanetComponent.vue';

export default {
  components: {
    Planet
  }
};
</script>

<style>
#app {
  display: flex;
  justify-content: space-around;
  align-items: center;
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
