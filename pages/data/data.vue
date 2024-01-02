<template>
    <div>
      {{ dateSidebar }}
    </div>
  </template>
  
  <script>
  export default {
    computed: {
      dateSidebar() {
        return this.$parent.$attrs['date-sidebar']
      }
    },
  }
  </script>