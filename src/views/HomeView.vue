<script setup>
    // props - onMounted (ao carregar a pagina)
    //         - reactive (tornar um componente reativo)
    //         - ref

import { onMounted, reactive, ref } from 'vue';
import ListPokemons from '../components/ListPokemons.vue'

let pokemons = reactive(ref())

onMounted(() => {
  fetch("https://pokeapi.co/api/v2/pokemon?limit=20&offset=0")
  .then(response => response.json())
  .then(response => {
    // console.log(response.results)
    pokemons.value = response.results
    console.log(pokemons)
  })
});

</script>

<template>
  <main>
    <div class="container">
      <div class="row mt-4">
        <div class="col-sm-12 col-md-6">
            <div class="card" style="width: 18rem;">
              <!-- <img src="https://assets.pokemon.com/assets/cms2/img/pokedex/full/025.png" class="card-img-top" alt="..."> -->
              <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a3/Cosplay_of_Pikachu%2C_Fanime_2015_%2818125488996%29.jpg/800px-Cosplay_of_Pikachu%2C_Fanime_2015_%2818125488996%29.jpg" class="card-img-top"  alt="...">
              <div class="card-body">
                <h5 class="card-title">Card Title</h5>
                <p class="card-text">Um pequeno texto aqui...</p>
              </div>
            </div>
        </div>
        <div class="col-sm-12 col-md-6">
          <div class="card">
            <div class="card-body row">
            <ListPokemons
            v-for="pokemon in pokemons"
            :key="pokemon.name"
            :name="pokemon.name"
            :url="pokemon.url"
          ></ListPokemons>
          </div>
          </div>
         
          <!-- <div class="card" style="width: 18rem;">
              <ul class="list-group">
                <li class="list-group-item" v-for="pokemon in pokemons" :key="pokemon.name">
                  {{ pokemon.name }}
                </li>
              </ul>
          </div> -->
         
          
          <!-- <div class="card" style="width: 18rem; height: 100%;" v-for="pokemon in pokemons" :key="pokemon.name">
            <img src="..." class="card-img-top" alt="...">
            <div class="card-body">
              <h5 class="card-title">{{pokemon.name}}</h5>
              <p class="card-text">{{ pokemon.url }}.</p>
              <a href="#" class="btn btn-primary">Go somewhere</a>
            </div>
          </div> -->


        </div>
      </div>
    </div>
  </main>
</template>
