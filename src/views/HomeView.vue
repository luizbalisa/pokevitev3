<template>
    <div class=" col-sm-12 col-md-6">
        <ul class="card card-list">
                <listaPokemons class="row card-body" v-for="(pokemon, index) in pokemons" :key="index" :name="pokemon.name" />
        </ul>
    </div>
</template>
<script setup>
import { onMounted, reactive, ref } from "vue";
import listaPokemons from "../components/ListPokemons.vue";

const pokemons = reactive(ref());

onMounted(() => {
    fetch("https://pokeapi.co/api/v2/pokemon?limit=250&offset=0")
        .then((res) => res.json())
        .then((data) => pokemons.value = data.results);
});
</script>

<style scoped>
.img {
    width: 250px;
}
</style>
