<script setup>
import { reactive } from 'vue';
import InputNumber from './components/InputNumber.vue';
import OperacaoSelect from './components/OperacaoSelect.vue';
import Resultado from './components/Resultado.vue';

const estado = reactive({
  numero1: null,
  numero2: null,
  operacao: 'soma',
  resultado: null,
});

const calcular = () => {
  const { numero1, numero2, operacao } = estado;

  const operacoes = {
    soma: (a, b) => a + b,
    subtracao: (a, b) => a - b,
    multiplicacao: (a, b) => a * b,
    divisao: (a, b) => b !== 0 ? (a / b).toFixed(2) : 'Não é possível dividir por zero',
  };

  estado.resultado = operacoes[operacao] ? operacoes[operacao](numero1, numero2) : null;
};

</script>

<template>
  <div class="container mt-5">
    <header class="p-4 mb-4 bg-primary text-white rounded-3 text-center">
      <h1 class="display-5">Calculadora</h1>
    </header>
    <div class="card shadow-sm">
      <div class="card-body">
        <form>
          <InputNumber :estado="estado" :calcular="calcular" />
          <OperacaoSelect :estado="estado" :calcular="calcular" />
        </form>
      </div>
    </div>
    <Resultado :resultado="estado.resultado" />
  </div>
</template>

<style scoped>
.container {
  max-width: 500px;
  margin: 0 auto;
}

header {
  background: #0d6efd;
  color: white;
}

.card {
  border: none;
}

.alert {
  font-size: 1.2rem;
}
</style>
