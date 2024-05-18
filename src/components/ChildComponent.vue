<template>
  <div class="child">
    <h2>Messenger</h2>
    <textarea v-model="message" cols="50" rows="10" placeholder="Tulis pesan Anda di sini..."></textarea>
    <button @click="sendMessageToParent" class="send-message-button">Kirim</button>
    <Modal v-if="showGrandchild" @close="showGrandchild = false">
      <GrandChildComponent @grandchildEvent="handleGrandchildEvent" />
    </Modal>
  </div>
</template>

<script>
import GrandChildComponent from './suii.vue';
import Modal from './Random.vue';

export default {
  name: 'ChildComponent',
  components: {
    GrandChildComponent,
    Modal,
  },
  data() {
    return {
      showGrandchild: false,
      message: 'isi deskripsi'
    };
  },
  methods: {
    sendMessageToParent() {
      this.$emit('childEvent', this.message);
    },
    handleGrandchildEvent(message) {
      this.$emit('childEvent', message);
    },
  },
};
</script>

<style scoped>
.child {
  width: 100%;
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
  border: 2px solid #1565c0;
  border-radius: 10px;
  background-color: #ffffff;
  box-shadow: 0px 0px 20px rgba(163, 0, 0, 0.1);
  transition: all 0.3s ease;
  text-align: center;
  font-family: 'Times New Roman', Times, serif;
  color: #000;
}

.child:hover {
  transform: translateY(-5px);
}

textarea {
  width: calc(100% - 40px);
  margin-bottom: 10px;
  font-family: 'Times New Roman', Times, serif;
  font-size: 16px;
  padding: 10px;
  border: 2px solid #ccc;
  border-radius: 5px;
  color: #000;
}

.open-modal-button,
.send-message-button {
  padding: 10px 20px;
  margin-top: 10px;
  margin-right: 10px;
  background-color: #2196f3;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.open-modal-button:hover,
.send-message-button:hover {
  background-color: #0d47a1;
}
</style>
