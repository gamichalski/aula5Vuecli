<template>
  <div id="app">
    <navbar>
      <a slot="brand" class="navbar-item" href="https://bulma.io">
        <img src="https://bulma.io/images/bulma-logo.png" alt="Bulma: Free, open source, and modern CSS framework based on Flexbox" width="112" height="28">
      </a>
      <a class="navbar-item" slot="start">
        Home
      </a>
      <a class="navbar-item" slot="end">
        Perfil
      </a>
    </navbar>
    <input class="input" placeholder="Digite sua pesquisa" v-model="filter"/>
    <list title="Buscas" :items="filteredItems"/>
  </div>
</template>

<script>
import Navbar from "./components/Navbar";
import List from "./components/List";
import items from "./items"

export default {
  name: "App",
  components: {
    List,
    Navbar
  },
  data() {
    return {
      items,
      filter: ""
    };
  },
  computed: {
    filteredItems(){
      return this.items.filter((item) => {
        return item.toLowerCase().includes(this.filter.toLowerCase())
      }).slice(0, 5);
    }
  } 
};
</script>

<style lang="scss">
@import "../node_modules/bulma/bulma.sass";
</style>
