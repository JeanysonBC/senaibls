# 🧩 Roteiro de Atividade Prática – JavaScript Básico com GitHub

## 🎯 Objetivo
Praticar conceitos fundamentais de **JavaScript**, utilizando **estruturas de decisão (if, else, switch)** e **estruturas de repetição (for, while, do...while)**, executando o código no **console do VS Code**, e por fim **publicando o projeto no GitHub**.

---

## 🧰 Requisitos
- Visual Studio Code instalado  
- Node.js instalado (para rodar o JS via terminal)
- Conta no GitHub configurada  
- Git instalado e configurado (usuário e e-mail)

---

## 🪜 Etapas da Atividade

### **1. Criação do projeto local**
1. Abra o **VS Code**.
2. Crie uma pasta chamada `atividade_javascript_basico`.
3. No terminal do VS Code, inicialize um repositório:
   ```bash
   git init
   ```
4. Crie um arquivo principal:
   ```bash
   touch app.js
   ```
5. Adicione um arquivo `.gitignore` com:
   ```
   node_modules/
   ```

---

### **2. Estrutura do código**
Abra o arquivo `app.js` e insira um cabeçalho de comentário:
```javascript
// Atividade prática – JavaScript básico
// Autor: [Seu nome]
// Data: [Data atual]
// Objetivo: praticar estruturas de controle e repetição
```

---

### **3. Exercício 1 – Estrutura de Decisão (if/else)**
Crie um código que leia uma idade e exiba se a pessoa é maior ou menor de idade.
```javascript
const prompt = require('prompt-sync')();

let idade = parseInt(prompt("Digite sua idade: "));

if (idade >= 18) {
  console.log("Você é maior de idade.");
} else {
  console.log("Você é menor de idade.");
}
```

---

### **4. Exercício 2 – Estrutura Condicional (switch)**
Crie um código que leia um número de 1 a 7 e informe o dia da semana.
```javascript
const dia = parseInt(prompt("Digite um número de 1 a 7: "));

switch (dia) {
  case 1: console.log("Domingo"); break;
  case 2: console.log("Segunda-feira"); break;
  case 3: console.log("Terça-feira"); break;
  case 4: console.log("Quarta-feira"); break;
  case 5: console.log("Quinta-feira"); break;
  case 6: console.log("Sexta-feira"); break;
  case 7: console.log("Sábado"); break;
  default: console.log("Número inválido.");
}
```

---

### **5. Exercício 3 – Estrutura de Repetição (for)**
Crie um programa que mostre todos os números de 1 a 10.
```javascript
for (let i = 1; i <= 10; i++) {
  console.log("Número:", i);
}
```

---

### **6. Exercício 4 – Estrutura de Repetição (while)**
Crie um programa que leia números até o usuário digitar 0.
```javascript
let numero = 1;

while (numero !== 0) {
  numero = parseInt(prompt("Digite um número (0 para sair): "));
  console.log("Você digitou:", numero);
}
```

---

### **7. Exercício 5 – Estrutura de Repetição (do...while)**
Crie um programa que solicite uma senha até o usuário acertar.
```javascript
let senha;
do {
  senha = prompt("Digite a senha: ");
} while (senha !== "1234");

console.log("Acesso liberado!");
```

---

### **8. Testes e Execução**
Execute os programas no terminal do VS Code:
```bash
node app.js
```
Faça testes de entrada e observe os resultados no console.

---

### **9. Controle de Versão (Git)**
Após finalizar os exercícios:
```bash
git add .
git commit -m "Atividade prática JS – estruturas de controle e loop"
```

---

### **10. Publicação no GitHub**
1. Crie um repositório no GitHub com o nome `atividade_javascript_basico`.
2. No VS Code, conecte o repositório remoto:
   ```bash
   git remote add origin https://github.com/SEU_USUARIO/atividade_javascript_basico.git
   git branch -M main
   git push -u origin main
   ```
3. Verifique se os arquivos estão disponíveis no repositório online.

---

### **11. Entrega**
- Envie o link do repositório público no GitHub para o instrutor.
- O código deve estar **comentado**, **organizado** e **funcionando via console**.

---
