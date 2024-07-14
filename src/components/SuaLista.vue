<template>
  <span class="subtitulo-lg sua-lista-texto"> Sua lista: </span>

  <ul v-if="ingredientes.length" class="ingredientes-sua-lista">
    <li
      v-for="ingrediente in ingredientes"
      :key="ingrediente"
      class="ingrediente"
    >
      <tag :texto="ingrediente" />
    </li>
  </ul>
  <p v-else class="paragrafo lista-vazia">
    <img src="./icones/lista-vazia.svg" alt="Ícone de pesquisa" />
    Sua lista está vazia, selecione ingredientes para iniciar.
  </p>
</template>

<script>
import Tag from './Tag.vue';

export default {
  components: { Tag },
  setup() {
    return {
      ingredientes: ["Alho", "Oregano", "ovo"],
    };
  },
};
</script>

<style scoped>
.sua-lista-texto {
  color: var(--coral, #f0633c);
  display: block;
  text-align: center;
  margin-bottom: 1.5rem;
}
.ingrediente:hover {
background-color: #c95433;
  color: rgb(255, 255, 255);
  cursor: pointer;
}

.ingredientes-sua-lista {
  display: flex;
  justify-content: center;
  gap: 1rem 1.5rem;
  flex-wrap: wrap;
}

.lista-vazia {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  gap: 0.25rem;

  color: var(--coral, #f0633c);
  text-align: center;
}

@media only screen and (max-width: 1300px) {
  .conteudo-principal {
    padding: 5rem 3.75rem;
    gap: 3.5rem;
  }
}

@media only screen and (max-width: 767px) {
  .conteudo-principal {
    padding: 4rem 1.5rem;
    gap: 4rem;
  }
}
</style>