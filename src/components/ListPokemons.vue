<template>
    <li class="col-4">
        <div class="card mb-4">
            <span class="text-center">{{ pokemon.name }}</span>
            <img class="p-10 card-img-top" src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/1.svg" alt="" /> 
        </div>
    </li>
</template>

<script setup>
const pokemon = defineProps(['name'])
</script>

<style lang="scss" scoped>

</style>