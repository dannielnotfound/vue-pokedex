<script setup>
import {ref} from 'vue'

</script>

<template>
  <!-- Menu Bootstrap -->
  <nav class="navbar navbar-expand-lg bg-dark text-light">
    <div class="container-fluid">
      <!-- <a class="navbar-brand" href="#">Navbar</a> -->
      <router-link class="navbar-brand text-light" to="/">Pokedex</router-link>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <router-link class="nav-link text-light" to="/">Home</router-link>
          </li>
          <li class="nav-item">
            <!-- <a class="nav-link text-light" href="#">Sobre</a> -->
            <router-link class="nav-link text-light" to="/about">Sobre</router-link>
          </li>
        </ul>
      </div>
    </div>
  </nav>


  <div class="main">
    <RouterView></RouterView>
  </div>

  <footer class="bg-dark text-light">
    <div>
      Unimar | ADS | {{ new Date().getFullYear() }}
    </div>
  </footer>
 
</template>
<style>
    footer{
      position: fixed;
      bottom: 0;
      width: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
      height: 60px;

    }
</style>