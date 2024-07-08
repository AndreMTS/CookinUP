
<template>
  <span class="tag">
      {{ texto }}
    </span>
 </template> 

<script>
export default {
    props: {
     texto: { type: String, required: true }
    }
}
</script>

<style> 
.ingrediente {
  display: inline-block;
  border-radius: 0.5rem;
  min-width: 4.25rem;
  padding: 0.5rem;
  text-align: center;
  transition: 0.2s;
  color: var(--creme, #fffaf3);
  background: var(--coral, #f0633c);
  font-weight: 700;
}

</style>
