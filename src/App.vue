<script></script>

<template>
  <nav class="navbar navbar-expand-md navbar-dark bg-primary">
    <div class="container-fluid">
      <router-link class="navbar-brand" to="/">
        <img src="./assets/logo.svg" alt="" height="40" class="d-inline-block align-text-center" />
        PokeVite
      </router-link>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav"
        aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav">
          <li class="nav-item">
            <router-link class="nav-link" to="/">Home</router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link" to="/about">About</router-link>
          </li>
        </ul>
      </div>
    </div>
  </nav>

  <div class="main container container text-body-secondary">
    <router-view></router-view>
  </div>
  
  <footer class="bg-primary text-light py-3 text-center">
    <div>
      <span>&copy {{new Date().getFullYear()}}</span>
    </div>
  </footer>

</template>

<style>
.bg-dark {
  background-color: #000;
}
footer {
  position: fixed;
  bottom: 0;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 50px;
  background-color: #343a40;
}
</style>
