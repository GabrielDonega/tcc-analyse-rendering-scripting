<template>
  <div class="teste-template">
    <componente-pai :nivel="3" v-for="i in 10000"/>
  </div>
</template>

<script setup>
import ComponentePai from "./components/ComponentePai.vue"

</script>

<style>
.teste-template {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: flex-start;
  gap: 10px;}
</style>

