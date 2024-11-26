<script setup>
import { reactive } from 'vue';

const estado = reactive({
  numero1: 0,
  numero2: 0,
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
          <div class="mb-3">
            <label for="numero1" class="form-label">Primeiro Número</label>
            <input id="numero1" type="number" v-model.number="estado.numero1" class="form-control" 
              placeholder="Digite um número" @input="calcular"/>
          </div>
          <div class="mb-3">
            <label for="numero2" class="form-label">Segundo Número</label>
            <input id="numero2" type="number" v-model.number="estado.numero2" class="form-control"
              placeholder="Digite outro número" @input="calcular"/>
          </div>
          <div class="mb-3">
            <label for="operacao" class="form-label">Operação</label>
            <select id="operacao" v-model="estado.operacao" class="form-select" @change="calcular">
              <option value="soma">Soma (+)</option>
              <option value="subtracao">Subtração (-)</option>
              <option value="multiplicacao">Multiplicação (×)</option>
              <option value="divisao">Divisão (÷)</option>
            </select>
          </div>
        </form>
      </div>
    </div>
    <div v-if="estado.resultado !== null" class="alert alert-info text-center mt-4">
      <strong>Resultado:</strong> {{ estado.resultado }}
    </div>
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
