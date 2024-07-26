<template>
  <div>
    <PlanetComponent name="Нейминг адрес сайта" :orbitSize="200" :initialAngle="0" :orbitSpeed="10" @click="openChat" />
    <PlanetComponent name="Прототипирование проекта" :orbitSize="300" :initialAngle="72" :orbitSpeed="15" @click="openChat" />
    <PlanetComponent name="Дизайн для Веба" :orbitSize="400" :initialAngle="144" :orbitSpeed="20" @click="openChat" />
    <PlanetComponent name="Вертска дизайна" :orbitSize="500" :initialAngle="216" :orbitSpeed="25" @click="openChat" />
    <PlanetComponent name="Обратная связь" :orbitSize="600" :initialAngle="288" :orbitSpeed="30" @click="openChat" />
  </div>
</template>

<script>
import PlanetComponent from '../Planet/PlanetComponent.vue';

export default {
  name: 'PlanetsContainer',
  components: {
    PlanetComponent
  },
  data() {
    return {
      isChatOpen: false
    };
  },
  props: {
    isExpanding: {
      type: Boolean,
      required: true
    }
  },
  methods: {
    openChat() {
      this.isChatOpen = true;
      this.$emit('open-chat');
    },
    closeChat() {
      this.isChatOpen = false;
    }
  }
};
</script>

<style scoped>
</style>
