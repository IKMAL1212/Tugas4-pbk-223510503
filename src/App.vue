<template>
  <div id="app">
    <div class="container">
      <ParentComponent />
    </div>
  </div>
</template>

<script>
import ParentComponent from './components/ParentComponent.vue';

export default {
  name: 'App',
  components: {
    ParentComponent,
  },
};
</script>


<style scoped>
.child {
  width: 100%;
  max-width: 500px;
  margin: 0 auto; 
  padding: 20px;
  border: 2px solid #1565c0;
  border-radius: 10px;
  background-color: #ffffff; 
  box-shadow: 0px 0px 20px rgba(163, 0, 0, 0.1);
  transition: all 0.3s ease;
  text-align: center;  
}

.child:hover {
  transform: translateY(-5px);
}

textarea {
  width: calc(100% - 20px); 
  margin-bottom: 10px;  
}

.open-modal-button,
.send-message-button {
  padding: 10px 20px;
  margin-top: 10px; 
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
