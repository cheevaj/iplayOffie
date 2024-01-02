<template>
    <div>
      <export :dateSidebar="'something'"/>
      {{ dateSidebar }}
    </div>
  </template>
  
  <script>
  export default {
    props: ['dateSidebar']
  }
  </script>
  