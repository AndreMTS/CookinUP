<template>
  <main class="conteudo-principal">
    <section>
      <SuaLista :ingredientes="ingredientes" />
    </section>
    <SelecionarIgredientes  @adicionar-ingrediente="adicionarIngrediente" @remover-ingrediente="removerIngrediente"/>
  </main>
</template>
<script lang="ts">
import { ref } from 'vue';
import SelecionarIgredientes from "./SelecionarIgredientes.vue";
import SuaLista from './SuaLista.vue';

export default {
  setup() {
    const ingredientes = ref<string[]>([]);

    function adicionarIngrediente(ingrediente: string) {
      ingredientes.value.push(ingrediente)
    }
    function removerIngrediente(ingrediente: string) {
      ingredientes.value = ingredientes.value.filter(iLista => ingrediente !== iLista);
    }

    return {
      ingredientes,
      adicionarIngrediente,
      removerIngrediente
    }
  },
  components: { SelecionarIgredientes, SuaLista },
}
</script>

<style scoped>
.conteudo-principal {
  padding: 6.5rem 7.5rem;
  border-radius: 3.75rem 3.75rem 0rem 0rem;
  background: var(--creme, #fffaf3);
  color: var(--cinza, #444);

  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 5rem;
}
</style>
