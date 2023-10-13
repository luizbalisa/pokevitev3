<script setup>
import { ref, computed } from "vue";

const nomeAluno = ref("Joacao");
const nota1 = ref(10);
const nota2 = ref(10);
const media = computed(() => {
  nota1.value + nota2.value / 2;
});

const rendaFamiliar = ref(2000);

const bolsista = computed(() => rendaFamiliar.value <= 2000);
</script>

<template>
  <div class="col">
    <h2>composition</h2>
    <div>
      <h3>{{ nomeAluno }}</h3>
      <input type="number" v-model="nota1" />
      <input type="number" v-model="nota2" />
    </div>
    <div>
      <p>Média</p>
      <hr />
      <input type="number" v-model="rendaFamiliar" />
    </div>
    <button class="btn" :class="bolsista ? btn-success : btn-danger">{{ bolsista }}</button> 
  </div>
</template>

<style scoped>
.col {
  display: flex;
  flex-direction: column;
  color: #4b0c07;
  background: #fff;
  padding: 20px;
  width: 550px;
  border: 1px solid #201c1c;
  border-radius: 20px;
  box-shadow: 0 0 12px 1px rgba(14, 5, 5, 0.2);
}
.btn {
  display: block;
  padding: 6px 16px;
  background-color: #fff;
  color: #4b0c07;
}

.btn-success {
  background-color: #4f9b22;
  color: #e6e6e6;
}

.btn-danger {
  background-color: #bd2e2e;
  color: #e6e6e6;
}
</style>
