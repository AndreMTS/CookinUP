<template>
  <Banners />
  <ConteudoPrincipal />
</template>

<script lang="ts">
import Banners from "./components/Banner.vue";
import ConteudoPrincipal from "./components/ConteudoPrincipal.vue";

export default {
  name: "Banner",
  components: { Banners, ConteudoPrincipal },
};
</script>

<style scoped>
</style>
