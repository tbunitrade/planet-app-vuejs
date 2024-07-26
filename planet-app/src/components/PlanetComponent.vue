<template>
  <div :class="['orbit', `orbit-${orbitSize}`]" :style="{top:`${initialTop}px`}" >
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
    },
    orbitSize:{
      type: Number,
      required: true
    },
    initialTop: {
      type: Number,
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
  left: 50%;
  animation: orbit 10s linear infinite;
}

.orbit-145 {
  width: 400px;
  height: 400px;
  margin: -200px;
}

.orbit-200 {
  width: 200px;
  height: 200px;
  margin: -100px;
}

.orbit-300 {
  width: 300px;
  height: 300px;
  margin:-150px;
}

.orbit-500 {
  width: 500px;
  height: 500px;
  margin:-250px;
}

.orbit-600 {
  width: 600px;
  height: 600px;
  margin: -300px;
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
