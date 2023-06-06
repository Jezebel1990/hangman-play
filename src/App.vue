<script setup>
import './css/global.css';


</script>

<template>
  <header>
    <nav class="navbar">
      <div class="navbar-logo">
          <img src="logo.png" alt="Logo">
      </div>
    </nav>
  </header>
  <main>
    <div id="app">
 <h1>Jogo da Forca</h1>

 <section id="inicio">
Inicio
 </section>

 <section id="jogo">
  Jogo
 </section>
 
    </div>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}

#app {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 100px;
}

</style>
