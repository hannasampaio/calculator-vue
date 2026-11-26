# 🧮 Calculadora em Vue.js

Calculadora feita com **Vue 3 (Composition API)** e **Bootstrap 5**: faz soma, subtração, multiplicação e divisão e mostra o resultado **em tempo real**, à medida que se escrevem os números ou se muda a operação.

🔗 **Demo:** [calculator-vue-black.vercel.app](https://calculator-vue-black.vercel.app)

![Vue.js](https://img.shields.io/badge/Vue.js-35495E?style=flat&logo=vuedotjs&logoColor=4FC08D)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat&logo=vite&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-7952B3?style=flat&logo=bootstrap&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=flat&logo=vercel&logoColor=white)

---

## 📸 Capturas de ecrã

| Ecrã inicial | Multiplicação | Divisão por zero |
|:---:|:---:|:---:|
| ![Ecrã inicial](screenshots/inicio.jpg) | ![Multiplicação](screenshots/multiplicacao.jpg) | ![Divisão por zero](screenshots/divisao-por-zero.jpg) |

## ✨ Funcionalidades

- As quatro operações: soma, subtração, multiplicação e divisão
- **Cálculo automático**, sem botão: o resultado atualiza a cada alteração
- Divisão com duas casas decimais
- **Validação da divisão por zero**, com mensagem de aviso

## 🧠 O que pratiquei

- **Composition API** com `<script setup>`
- **Estado reativo** com `reactive()`
- **Componentização**: a aplicação começou num só ficheiro e foi depois dividida em componentes (`InputNumber`, `OperacaoSelect`, `Resultado`)
- Comunicação entre componentes com **props** (`defineProps`)
- **Renderização condicional** com `v-if`
- Mapa de operações num objeto, em vez de vários `if/else`
- Layout com **Bootstrap 5** (card, formulário e alerta)

## 📁 Estrutura

```
src/
├── components/
│   ├── InputNumber.vue      # Campos dos dois números
│   ├── OperacaoSelect.vue   # Escolha da operação
│   └── Resultado.vue        # Mostra o resultado
├── App.vue                  # Estado e lógica de cálculo
└── main.js
```

## ▶️ Como executar

```bash
git clone https://github.com/hannasampaio/calculator-vue.git
cd calculator-vue
npm install
npm run dev
```

## 📚 Contexto

Projeto desenvolvido no âmbito da formação **Full Stack Java da EBAC** (módulo de Vue.js), em 2024.

---

Desenvolvido por **Hanna Sampaio** · [LinkedIn](https://www.linkedin.com/in/hannasampaio7/) · [GitHub](https://github.com/hannasampaio)
