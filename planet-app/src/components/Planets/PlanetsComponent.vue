<template>
  <div>
    <Planet name="Нейминг адрес сайта" :orbitSize="300" :initialAngle="1000" :orbitSpeed="17" v-if="!isExpanding" />
    <Planet name="Прототипирование проекта" :orbitSize="500" :initialAngle="1000" :orbitSpeed="15" v-if="!isExpanding" />
    <Planet name="Дизайн для Веба" :orbitSize="550" :initialAngle="1000" :orbitSpeed="20" v-if="!isExpanding" />
    <Planet name="Вертска дизайна" :orbitSize="500" :initialAngle="1000" :orbitSpeed="25" v-if="!isExpanding" />
    <Planet name="Обратная связь" :orbitSize="600" :initialAngle="1000" :orbitSpeed="30" v-if="!isExpanding" />
  </div>
</template>

<script>
import Planet from '../Planet/PlanetComponent.vue';

export default {
  name: 'PlanetsComponent',
  components: {
    Planet
  },
  props: {
    isExpanding: {
      type: Boolean,
      required: true
    }
  }
};
</script>

<style scoped>
</style>
