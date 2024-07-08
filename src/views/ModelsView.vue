<template>
    <div class="post">
      <h1>Modals</h1>
      <button @click="showModal = true">Show modal</button>
      <Teleport to="body">
      <div class="modal" v-if="showModal">
        <h1>This is a modal</h1>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quam, esse explicabo officiis sit, aliquid sequi natus veritatis deleniti iusto, aspernatur optio quasi. Ullam voluptate similique ipsam perferendis quo reprehenderit consectetur</p>
        <button @click="showModal = false">Hide modal</button>
      </div>
      </Teleport>
    </div>
  </template>
  
  <script setup>
    import { ref } from 'vue';
    const showModal = ref(false);

  </script>
  
  <style scoped>
    .modal {
      background: beige;
      padding: 10px;
      border-radius: 10px;
      top: 20px;
      left: 20px;
      right: 20px;
      bottom: 20px;
    }
  </style>