<template>
    <nuxt-child :test="'RESOLVE_PLZ'"/>
  </template>
<script>
export default {
  props: ["test"],
  mounted() {
    console.log(this.test) // RESOLVE_PLZ
  }
}
</script>