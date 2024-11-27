<script setup>
  const props = defineProps(['estado', 'calcular']);
</script>

<template>
  <div class="mb-3">
    <label for="numero1" class="form-label">Primeiro Número</label>
    <input id="numero1" type="number" :value="props.estado.numero1" @input="(e) => { props.estado.numero1 = e.target.valueAsNumber; props.calcular(); }"
      placeholder="Digite um número" class="form-control"/>
  </div>
  <div class="mb-3">
    <label for="numero2" class="form-label">Segundo Número</label>
    <input 
      id="numero2" type="number" :value="props.estado.numero2" @input="(e) => { props.estado.numero2 = e.target.valueAsNumber; props.calcular(); }"
      placeholder="Digite outro número" class="form-control"/>
  </div>
</template>
