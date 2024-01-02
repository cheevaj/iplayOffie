<!-- pages/index.vue -->

<template>
    <div>
      <Button @click="showMessage">Click me!</Button>
    </div>
  </template>
  
  <script>
  export default {
    methods: {
      showMessage() {
        this.$Message.info('Hello, iView!');
      }
    }
  };
  </script>
  