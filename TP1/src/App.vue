<script setup>
import { ref } from 'vue';
import TheHeader from './components/TheHeader.vue';

const temperature = ref(0);
</script>

<template>
  <TheHeader />
  <div>  <button @click="temperature++"> {{ temperature }} </button>
</div>
</template>

<style scoped>

div{
  display: flex;
  justify-content: center;
  align-items: center;
  height: 80vh;
}
  
  button{
    cursor: pointer;
    background-color: yellow;
    border-radius: 99px;
    width: 10%;
    font-size: 40px;
  }
</style>

