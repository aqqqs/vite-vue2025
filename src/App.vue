<template>

<div class="main">
  <button @click="count--">-</button>
  <div>{{ count }}</div>
  <button @click="count++">+</button>
</div>

</template>

<script setup>
import {ref} from 'vue';

const count = ref(0)


</script>

<style scoped>
.main {
  display: flex;
  flex-direction: row;
}
div {

  margin: 10%;
}
</style>
