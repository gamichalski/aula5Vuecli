<template>
  <div id="app">
    <input class="input" placeholder="Digite sua pesquisa" v-model="filter"/>
    <list title="Buscas" :items="filteredItems"/>
  </div>
</template>

<script>
import List from "./components/List";
import items from "./items"

export default {
  name: "App",
  components: {
    List
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
