<template>
  <div class="Random-overlay" @click.self="$emit('close')">
    <div class="Random">
      <button class="close-button" @click="$emit('close')">Close</button>
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Random',
};
</script>

<style scoped>
.Random-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: #ffffff;
  display: flex;
  justify-content: center;
  align-items: center;
}

.Random {
  background: #ffffff;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.5);
  width: 80%;
  max-width: 600px;
  text-align: center;
}

.close-button {
  position: absolute;
  top: 10px;
  right: 10px;
  padding: 5px 10px;
  background-color: #ffffff;
  color: #333;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}
.close-button:hover {
  background-color: #ffffff;
}

</style>
