<template>
  <main class="conteudo-principal">
    <section>
      <SuaLista :ingredientes="ingredientes" />
    </section>
    <SelecionarIgredientes  @adicionar-ingrediente="adicionarIngrediente" @remover-ingrediente="removerIngrediente"/>
  </main>
</template>
<script lang="ts">
import SelecionarIgredientes from "./SelecionarIgredientes.vue";
import SuaLista from "./SuaLista.vue";

export default {
  components: { 
    SelecionarIgredientes,
    SuaLista
    },
  data() {
    return {
      ingredientes: [] as string[],
    };
  },
  methods: {
    adicionarIngrediente(ingrediente: string) {
      this.ingredientes.push(ingrediente)
    },
    removerIngrediente(ingrediente: string) {
  this.ingredientes = this.ingredientes.filter((lista: string) => ingrediente !== lista);
}
  }
};
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
