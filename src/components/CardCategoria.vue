<template>
  {{ categoria.nome }}
  {{ categoria.imagem }}
</template>


<script lang="ts">
import type { PropType } from "vue";
import type ICategorias from "@/interfaces/ICategoria";
export default {
  props: {
    categoria: { type: Object as PropType<ICategorias>, required: true },
  },
};
</script>
