<template>
    <div class="container">
        <div class="row">
            <ul class="card" v-for="(pokemon, index) in pokemons" :key="index">
                <listaPokemons :name="pokemon.name" />
            </ul>
        </div>
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
