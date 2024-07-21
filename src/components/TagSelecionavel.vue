<template>
  <button class="ingrediente" @click="aoClicar" :aria-pressed="selecionado">
    <tag :texto="ingrediente" :ativa="selecionado" />
  </button>
</template>

<script>
import Tag from "./Tag.vue";

export default {
  components: { Tag },
  props: {
    ingrediente: { type: String, required: true },
  },
  data() {
    return {
      selecionado: false,
    };
  },
  methods: {
    aoClicar() {
      this.selecionado = !this.selecionado;
      if (this.selecionado){
        this.$emit('adicionarIngrediente', this.ingrediente)
      }else {
        this.$emit('removerIngrediente', this.ingrediente);
      }
    },
  },
  emits: ['adicionarIngrediente', 'removerIngrediente']
};
</script>

<style scoped>
.ingrediente {
  cursor: pointer;
}
</style>