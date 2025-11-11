<script setup>
import {ref} from 'vue';

const text = ref('новое')

function changeText () {
  text.value = ('обновленно')
  show.value = !show
}

const ssrHtml = '<h1> Заголовок с сервера <h1> '

const goods = ['Верняя одежда', 'Футболки', 'Толстовки', 'Джинсы', 'Шорты' ]

const show = (false)

</script>


<template>
  <!-- v-html -->
  <div v-html="ssrHtml" ></div>
  <!-- v-on -->
  <div class="container">
    <p v-on:click="changeText()">Событие {{ text }}</p>
  </div>
  <!-- v-for -->
  <div>
    <ol>
      <li v-for="good in goods" :key="good">{{ good }}</li>
    </ol>
  </div>
  <!-- v-show -->
  <div v-show="show"></div>
  <!-- v-if -->
  <button v-if="Math.random() > 20"> видно</button>
  <div v-else="false">скрыто</div>
  <!-- v-bind -->
  <div :style="{color: 'green'}"> Продукты </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: row;
  width: 100%;
  background-color: beige;
}
p {
  display: flex;
  font-family: 'Courier New', Courier, monospace;
  font-size: larger;
  font-weight: 500;
  color: cadetblue;
  flex-direction: column;
  margin: 10%;
  width: 100%;
  background-color: brown;
}
</style>
