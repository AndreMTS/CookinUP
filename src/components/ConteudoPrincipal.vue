<template>
  <main class="conteudo-principal">
    <section>
      <SuaLista :ingredientes="ingredientes" />
    </section>
    <KeepAlive include="SelecionarIngredientes">
      <SelecionarIngredientes
        v-if="conteudo === 'SelecionarIngredientes'"
        @adicionar-ingrediente="adicionarIngrediente"
        @remover-ingrediente="removerIngrediente"
        @buscarReceita="navegar('MostrarReceitas')"
      />
      <MostrarReceitas
        v-else-if="conteudo === 'MostrarReceitas'"
        :ingredientes="ingredientes"
        @editar-receitas="navegar('SelecionarIngredientes')"
      />
    </KeepAlive>
  </main>
</template>
<script lang="ts">
import SelecionarIngredientes from "./SelecionarIngredientes.vue";
import SuaLista from "./SuaLista.vue";
import MostrarReceitas from "./MostrarReceitas.vue";

type Pagina = "SelecionarIngredientes" | "MostrarReceitas";

export default {
  data() {
    return {
      ingredientes: [] as string[],
      conteudo: "SelecionarIngredientes" as Pagina,
    };
  },
  components: { SelecionarIngredientes, SuaLista, MostrarReceitas },
  methods: {
    adicionarIngrediente(ingrediente: string) {
      this.ingredientes.push(ingrediente);
    },
    removerIngrediente(ingrediente: string) {
      this.ingredientes = this.ingredientes.filter(
        (iLista) => ingrediente !== iLista
      );
    },
    navegar(pagina: Pagina) {
      this.conteudo = pagina;
    },
  },
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
