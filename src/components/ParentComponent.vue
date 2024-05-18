<template>
  <div class="parent">
    <h2 class="header">Welcome to Parent Components</h2>
    <div class="content">
      <p class="instruction">This is a parent component where you can:</p>
      <ul>
        <li class="instruction">Write and edit messages</li>
        <li class="instruction">Open a child component</li>
      </ul>
    </div>
    <div class="actions">
      <textarea v-model="message" cols="30" rows="10"></textarea>
      <button @click="showChild = true" class="open-modal-button">Open Child Component</button>
    </div>
    <Modal v-if="showChild" @close="showChild = false">
      <ChildComponent @childEvent="updateMessage" />
    </Modal>
  </div>
</template>

<script>
import ChildComponent from './ChildComponent.vue';
import Modal from './Random.vue';

export default {
  name: 'ParentComponent',
  components: {
    ChildComponent,
    Modal,
  },
  data() {
    return {
      message: 'This is the parent component message',
      showChild: false,
    };
  },
  methods: {
    updateMessage(newMessage) {
      this.message = newMessage;
    },
  },
};
</script>

<style scoped>

.parent {
  width: 100vw;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 20px;
  border: 2px solid #1565c0;
  border-radius: 10px;
  background-color: #f0f0f0 !important;
  box-shadow: 0px 0px 20px rgba(163, 0, 0, 0.1);
  transition: all 0.3s ease;
  text-align: center;
}

.parent:hover {
  transform: translateY(-5px);
}

.content {
  margin-bottom: 20px;
  margin: auto; 
  color: #000; 
}

.actions {
  display: flex;
  align-items: center;
  margin: auto;
}

textarea {
  flex: 1;
  padding: 10px;
  font-family: 'Times New Roman', Times, serif;
  font-size: 18px;
  border: 2px solid #ffffff;
  border-radius: 5px;
  resize: vertical;
  margin-right: 10px;
  background-color: #ffffff;
  color: #000;
  height: 100px;
}

.header {
  font-size: 24px;
  color: #000;
  margin-bottom: 10px;
}

.open-modal-button {
  padding: 10px 20px;
  background-color: #2196f3;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.open-modal-button:hover {
  background-color: #0d47a1;
}

</style>
