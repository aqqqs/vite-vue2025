<script setup>
import {ref} from 'vue';

const text = ref('новое')

const show = ref(false)

function changeText () {
  text.value = ('обновлено')
  show.value = !show.value
}

const ssrHtml = '<h1> Заголовок с сервера <h1> '

const goods = ['Верняя одежда', 'Футболки', 'Толстовки', 'Джинсы', 'Шорты' ]


</script>


<template>
  <!-- v-html -->
  <div v-html="ssrHtml" ></div>
  <!-- v-on -->
  <div class="container">
    <div v-on:click="changeText()">Событие клик {{ text }}</div>
    <!-- v-show -->
    <div v-show="show">{{ text }}</div>
    <!-- v-if -->
    <div v-if="show">{{ text }}</div>
    <div v-else="false"></div>
  </div>
  <!-- v-bind -->
    <h2 :style="{color: 'green'}"> Продукты </h2>
  <!-- v-for -->
    <div>
      <ol>
        <li v-for="good in goods" :key="good">{{ good }}</li>
      </ol>
    </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  width: 100%;
  color: red;
  background-color: beige;
}

</style>
