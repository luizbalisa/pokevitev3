<template>
    <div class="container">
        <div class="row">
            <!-- <article class="col card mt-5">
                <img class="p-10 img"
                    src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/1.svg"
                    alt="" />
                <div class="cart-body">

                    <h1 class="title">poke</h1>
                    <p class="subtitle">
                        Lorem ipsum dolor sit amet consectetur adipisicing elit. At quidem
                        consequatur quod aspernatur cum sapiente accusantium nulla magni
                        quasi modi, enim explicabo aut eveniet sequi sit dolorem incidunt
                        ullam asperiores.
                    </p>
                </div>
            </article> -->
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
