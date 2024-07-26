<template>
  <div class="orbit">
    <div class="planet" @mouseover="isHovered = true" @mouseleave="isHovered = false">
      <div v-if="isHovered" class="tooltip">{{ name }}</div>
    </div>
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
.orbit {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 200px;
  height: 200px;
  margin: -100px 0 0 -100px;
  animation: orbit 10s linear infinite;
}

.planet {
  width: 100px;
  height: 100px;
  background-color: gray;
  border-radius: 50%;
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  transition: transform 0.3s ease;
}

.planet:hover {
  transform: translateX(-50%) scale(1.2);
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

@keyframes orbit {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
</style>
