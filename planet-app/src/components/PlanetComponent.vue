<template>
  <div class="planet" @mouseover="isHovered = true" @mouseleave="isHovered = false">
    <div v-if="isHovered" class="tooltip">{{ name }}</div>
  </div>
</template>

<script>
export default {
  name: 'PlanetComponent',
  props: {
    name: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      isHovered: false
    };
  }
};
</script>

<style scoped>
.planet {
  width: 100px;
  height: 100px;
  background-color: gray;
  border-radius: 50%;
  position: relative;
  transition: transform 0.3s ease;
}
.planet:hover {
  transform: scale(1.2);
}
.tooltip {
  position: absolute;
  top: -20px;
  left: 50%;
  transform: translateX(-50%);
  background-color: black;
  color: white;
  padding: 5px;
  border-radius: 5px;
}
</style>
