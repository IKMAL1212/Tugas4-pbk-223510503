<template>
  <div class="grandchild">
    <h2>Grandchild Component</h2>
    <textarea v-model="message" cols="30" rows="10"></textarea>
    <button @click="sendMessageToChild" class="send-button">Kirim</button>
  </div>
</template>

<script>
export default {
  name: 'GrandchildComponent',
  data() {
    return {
      message: 'selanjutnya'
    };
  },
  methods: {
    sendMessageToChild() {
      this.$emit('grandchildEvent', this.message);
    },
  },
};
</script>

<style scoped>

.grandchild {
  padding: 20px;
  border: 2px solid #ffffff;
  border-radius: 10px;
  margin-top: 15px;
  background-color: #ffffff;
  transition: all 0.3s ease;
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.grandchild:hover {
  background-color: #f0f0f0;
}

.send-button {
  padding: 10px 20px;
  background-color: #ffffff;
  color: #ff0000;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
  font-family: 'Times New Roman', Times, serif;
}

.send-button:hover {
  background-color: #f0f0f0;
}

textarea {
  width: 90%;
  padding: 10px;
  font-family: 'Times New Roman', Times, serif;
  font-size: 18px;
  border: 2px solid #ffffff;
  border-radius: 5px;
  resize: vertical;
  margin-bottom: 10px;
  text-align: center;
  background-color: #ffffff;
  color: #333;
  height: 50%;
}

h2 {
  font-size: 24px;
  margin-bottom: 20px;
  color: #333; /* Perbaiki warna teks */
  font-family: 'Times New Roman', Times, serif; /* Ubah font */
}

</style>
