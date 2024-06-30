<template>
  <article class="categoria">
    <header class="categoria__cabecalho">
      <img
        :src="`/images/icones/categorias_ingredientes/${categoria.imagem}`"
        alt=""
        class="categoria__imagem"
      />
      <h2 class="paragrafo-lg categoria__nome">{{ categoria.nome }}</h2>
    </header>
    <ul class="categoria__ingredientes">
      <li v-for="ingrediente in categoria.ingredientes" :key="ingrediente">
        {{ ingrediente }}
      </li>
    </ul>
  </article>
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

<style>
.categoria {
  width: 19.5rem;
  padding: 1rem;
  border-radius: 1rem;
  background: var(--branco, #fff);
  box-shadow: 4px 4px 10px 0px rgba(68, 68, 68, 0.05);
  height: 100%;

  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2rem;
}

.categoria__cabecalho {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
}

.categoria__imagem {
  width: 3.5rem;
}

.categoria__nome {
  text-align: center;
  color: var(--verde-medio, #3d6d4a);
  font-weight: 700;
}

.categoria__ingredientes {
  display: flex;
  justify-content: center;
  gap: 0.5rem;
  flex-wrap: wrap;
}

.categoria__ingredientes li {
  background-color: #efefef;
  padding: 8px;
  border-radius: 8px;
}

.categoria__ingredientes li:hover {
  background-color: #f0633c;
  color: #efefef;
  cursor: pointer;
  padding: 8px;
  border-radius: 8px;
}
</style>
