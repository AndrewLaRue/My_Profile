<template>
  <section class="cover-img text-light">
    <header class="container ">
      <div class="row pt-3 align-items-center text-center">
        <h1 class="col-md-3 ">
          Andrew LaRue
        </h1>
        <h2 class="col-md-9 ">Software Developer</h2>
      </div>
    </header>
    <main class="container">
      <router-view />
    </main>
    <footer class="container fixed-bottom">
      <div class="row align-items-center justify-content-center">
        <small class="col-md-4 text-center text-uppercase no-select px-0">
          Background photo by
          <a class="text-light selectable no-select" href="https://unsplash.com/@alesnesetril">Ales Nesetril</a>
          on
          <a class="text-light selectable no-select" href="https://unsplash.com/">unsplash</a>
        </small>
      </div>
    </footer>
  </section>
</template>

<script>
import { computed } from 'vue';
import { AppState } from './AppState';

export default {
  name: 'App',
  setup() {
    return {
      appState: computed(() => AppState)
    }
  }
}
</script>
<style lang="scss">
@import "./assets/scss/main.scss";

.cover-img {
  background-image: url(https://images.unsplash.com/photo-1531297484001-80022131f5a1?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2020&q=80);
  background-position: center;
  background-size: cover;
  height: 100vh;
}

a {
  text-decoration: none;
  font-weight: 700;
}

h1,
h2,
small {
  font-family: 'Oswald', sans-serif;
}

small {
  filter: brightness(20%);
}

small:hover {
  filter: brightness(100%) !important;
}
</style>
