<script setup>
  const props = defineProps(['estado', 'calcular']);
</script>

<template>
  <div class="mb-3">
    <label for="operacao" class="form-label">Operação</label>
    <select id="operacao" :value="props.estado.operacao" @change="(e) => { props.estado.operacao = e.target.value; props.calcular(); }" class="form-select">
      <option value="soma">Soma (+)</option>
      <option value="subtracao">Subtração (-)</option>
      <option value="multiplicacao">Multiplicação (×)</option>
      <option value="divisao">Divisão (÷)</option>
    </select>
  </div>
</template>
