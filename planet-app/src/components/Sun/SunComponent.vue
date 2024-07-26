<template>
  <div class="sun" @click="expandSun" :class="{ expanding: isExpanding }"></div>
</template>

<script>
export default {
  name: 'SunComponent',
  data() {
    return {
      isExpanding: false
    };
  },
  methods: {
    expandSun() {
      this.isExpanding = true;
      this.$emit('expand'); // Emit event to notify parent component
    }
  }
};
</script>

<style scoped>
.sun {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 100px;
  height: 100px;
  background-color: yellow;
  border-radius: 50%;
  transform: translate(-50%, -50%);
  box-shadow: 0 0 50px rgba(255, 255, 0, 0.7);
  transition: all 5s ease;
}

.sun.expanding {
  width: 200vw;
  height: 200vh;
  background-color: red;
  transform: translate(-50%, -50%) scale(2);
  transition: all 10s ease;
}
</style>
