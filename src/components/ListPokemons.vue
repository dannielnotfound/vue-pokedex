<script setup>
    const pokemon = defineProps(["name", "url"])
    const idPokemon = pokemon.url.split('/')[6]
    const imageUrl = "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/dream-world/"+ idPokemon + ".svg"
   
</script>

<template>
    <div class="col-md-4">
        <div class="card mb-3 p-2">
            <img 
            :src="imageUrl"
            class="card-img-top"
            alt="..."
            height="90">
            <div class="card-body">
                <p class="card-title text-center">{{ pokemon.name.charAt(0).toUpperCase() + pokemon.name.slice(1)}}</p>
                <!-- <p class="card-text">{{ pokemon.url }}</p> -->
            </div>
        </div>
    </div>
</template>

<style>

</style>