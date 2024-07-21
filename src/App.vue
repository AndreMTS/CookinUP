<template>
  <Banners />
  <ConteudoPrincipal />
  <Rodape />
</template>

<script lang="ts">
import Banners from "./components/Banner.vue";
import ConteudoPrincipal from "./components/ConteudoPrincipal.vue";
import Rodape from './components/Rodape.vue';

export default {
  name: "Banner",
  components: { Banners, ConteudoPrincipal, Rodape },
};
</script>

<style scoped>
</style>
