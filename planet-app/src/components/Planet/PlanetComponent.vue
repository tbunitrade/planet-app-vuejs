<template>
  <div :class="['orbit', `orbit-${orbitSize}`]" :style="orbitStyle">
    <div class="planet" :style="planetStyle" @mouseover="isHovered = true" @mouseleave="isHovered = false">
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
    orbitSize: {
      type: Number,
      required: true
    },
    initialAngle: {
      type: Number,
      required: true
    },
    orbitSpeed: {
      type: Number,
      required: true
    }
  },
  data() {
    return {
      isHovered: false
    };
  },
  computed: {
    orbitStyle() {
      return {
        width: `${this.orbitSize}px`,
        height: `${this.orbitSize}px`,
        top: `calc(50% - ${this.orbitSize / 2}px)`,
        left: `calc(50% - ${this.orbitSize / 2}px)`,
        animationDuration: `${this.orbitSpeed}s`,
        transformOrigin: 'center center',
        transform: `rotate(${this.initialAngle}deg)`
      };
    },
    planetStyle() {
      const angleInRadians = (this.initialAngle * Math.PI) / 180;
      const x = (this.orbitSize / 2) * Math.cos(angleInRadians);
      const y = (this.orbitSize / 2) * Math.sin(angleInRadians);
      return {
        transform: `translate(${x}px, ${y}px)`
      };
    }
  }
};
</script>

<style scoped>
.orbit {
  position: absolute;
  animation: orbit linear infinite;
}

.planet {
  width: 100px;
  height: 100px;
  background-color: gray;
  border-radius: 50%;
  position: absolute;
  top: 50%;
  left: 50%;
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

@keyframes orbit {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
</style>
