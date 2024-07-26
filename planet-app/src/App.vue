<template>
  <div id="app">
    <SunComponent @expand="handleSunExpand" />
    <PlanetsContainer :isExpanding="isExpanding" @open-chat="openChat" />
    <ChatWindow :isOpen="isChatOpen" @close="closeChat" />
  </div>
</template>

<script>
import SunComponent from './components/Sun/SunComponent.vue';
import PlanetsContainer from './components/Planets/PlanetsContainer.vue';
import ChatWindow from './components/Chat/ChatWindow.vue';

export default {
  components: {
    SunComponent,
    PlanetsContainer,
    ChatWindow
  },
  data() {
    return {
      isExpanding: false,
      isChatOpen: false
    };
  },
  methods: {
    handleSunExpand() {
      this.isExpanding = true;
    },
    openChat() {
      this.isChatOpen = true;
    },
    closeChat() {
      this.isChatOpen = false;
    }
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
