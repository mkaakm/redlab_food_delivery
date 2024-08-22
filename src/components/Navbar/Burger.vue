<template>
    <div class="burger-button" @click="toggleMenu">
      <div :class="['bar', { 'open': isOpen }]" ></div>
      <div :class="['bar', { 'open': isOpen }]" ></div>
      <div :class="['bar', { 'open': isOpen }]" ></div>
    </div>
  </template>
  
  <script setup>
  import { ref, defineEmits } from 'vue';
  
  const isOpen = ref(false);
  const emit = defineEmits(['toggle'])
  function toggleMenu() {
    emit('toggle');
    isOpen.value = !isOpen.value;
  }
  </script>
  
  <style scoped>
  .burger-button {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    cursor: pointer;
    width: 40px;
    height: 30px;
    position: relative; 
  }
  
  .bar {
    width: 30px;
    height: 3px;
    background-color: black;
    margin: 4px 0;
    transition: 0.3s ease;
  }
  
  .bar.open:nth-child(1) {
    transform: rotate(45deg);
    position: absolute;
    top: 13px;
  }
  
  .bar.open:nth-child(2) {
    opacity: 0;
  }
  
  .bar.open:nth-child(3) {
    transform: rotate(-45deg);
    position: absolute;
    top: 13px;
  }
  @media (min-width: 768px) {
    .burger-button{
        display: none;
    }
  }
  </style>
  