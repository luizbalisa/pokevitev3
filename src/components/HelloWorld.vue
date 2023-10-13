<script setup>
import { ref } from 'vue'

const nomeAluno = ref('Joacao');
const nota1 = ref(10);
const nota2 = ref(10);
const media = computed(()=> {nota1.value + nota2.value / 2});

const rendaFamiliar = ref(2000)

const bolsista = computed(()=> rendaFamiliar.value <= 2000);
 
</script>

<template>
  <div class="col">
  <h2>composition</h2>
  <h3>{{nomeAluno}}</h3> 
</div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
