<script setup>
const bascule = ref(true);
const toto = ref('A');
const notes = ref([10, 12, 15, 8, 5]);
const items = [{ message: 'Foo' }, { message: 'Bar' }]
const myObject = {
  title: 'How to do lists in Vue',
  author: 'Jane Doe',
  publishedAt: '2016-04-10'
}
import { ref } from 'vue';
</script>

<template>
  <h1>Mon exo TD 01</h1>
  <hr>
  <p>exo 1 : gestion du v-if et v-else</p>

  <button @click="bascule = !bascule; console.log(bascule)">Basculer</button>

  <h1 v-if="bascule">Vue est magnifique</h1>
  <h1 v-else>Oh non 😢</h1>

  <hr>

  <p>exo 2 : gestion du v-else-if</p>

  <button @click="toto = 'A';">Mettre A</button>
  <button @click="toto = 'B';">Mettre B</button>
  <button @click="toto = 'C';">Mettre C</button>
  <button @click="toto = 'D';">Aucun</button>

<h1 v-if="toto==='A'">C'est A</h1>
<h1 v-else-if="toto==='B'">C'est B</h1>
<h1 v-else-if="toto==='C'">C'est C</h1>
<h1 v-else="toto==='C'">C'est pas du A ni du B ni du C</h1>

<hr>

<p>exo 3 : gestion des notes </p>

<p>Notes : {{ notes[0] }}
   <span v-if="notes[0] < 10">bêteuh</span>
   <span v-else>Nickel</span>
</p>

<p>Notes : {{ notes[1] }}
   <span v-if="notes[1] < 10">bêteuh</span>
   <span v-else>Nickel</span>
</p>

<p>Notes : {{ notes[2] }}
   <span v-if="notes[2] < 10">bêteuh</span>
   <span v-else>Nickel</span>
</p>

<p>Notes : {{ notes[3] }}
   <span v-if="notes[3] < 10">bêteuh</span>
   <span v-else>Nickel</span>
</p>

<p>Notes : {{ notes[4] }}
   <span v-if="notes[4] < 10">bêteuh</span>
   <span v-else>Nickel</span>
</p>

<hr>

<p>exo 4 : Les boucles for </p>

<li v-for="item in items">
  {{ item.message }}
</li>

<hr>

<p>exo 5 : Les objets </p>

<table>
  <tr>
    <th>Key</th>
    <th>Value</th>
  </tr>
  <tr v-for="(value, key) in myObject">
    <td>{{ key }}</td>
    <td>{{ value }}</td>
  </tr>
</table>

<span v-for="n in 10"></span>

<hr>

<p>exo 6 : Exo final : table avec couleur </p>

<p>afficher toutes les notes dans un tableau</p>

<table>
  <tr>
    <th>Note</th>
  </tr>
    <tr v-for="note in notes">
      <td :style="{ color: note < 10 ? 'red' : note < 15 ? 'orange' : 'green' }">{{ note }}/20</td>
    </tr>
</table>


</template>

<style scoped>
table, th, td {
  border: 1px solid black;
  border-collapse: collapse;
  padding: 5px;
}
</style>
