<template>
  <div class="chat-window" v-if="isOpen">
    <button class="close-button" @click="closeChat">X</button>
    <div class="chat-content">
      <!-- Здесь можно добавить ваш чат или iframe с чатом -->
      <p>Добро пожаловать в чат! Как мы можем помочь вам сегодня?</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ChatWindow',
  props: {
    isOpen: {
      type: Boolean,
      required: true
    }
  },
  methods: {
    closeChat() {
      this.$emit('close');
    }
  }
};
</script>

<style scoped>
.chat-window {
  position: fixed;
  bottom: 20px;
  right: 20px;
  width: 300px;
  height: 400px;
  background-color: white;
  border: 1px solid #ccc;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  z-index: 1000;
}

.close-button {
  position: absolute;
  top: 10px;
  right: 10px;
  background: none;
  border: none;
  font-size: 18px;
  cursor: pointer;
}

.chat-content {
  padding: 20px;
  height: calc(100% - 40px);
  overflow-y: auto;
}
</style>
