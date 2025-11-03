# 🧠 Atividade Prática – Git + JavaScript + GitHub

## 🎯 Objetivo
Criar um mini-projeto em JavaScript, versionar com Git (incluindo branch e merge) e publicar no GitHub via **SSH**, utilizando apenas o **terminal Bash do VS Code**.

---

## 🧩 Etapa 1 – Criar o projeto e iniciar o Git

```bash
mkdir js-contador && cd js-contador
git init
git config user.name "Seu Nome"
git config user.email "seu-email@exemplo.com"
```

---

## 🧾 Etapa 2 – Criar os arquivos

### **README.md**
```bash
cat > README.md << 'EOF'
# js-contador
Exemplo básico de JavaScript: contador com soma, validação e loop.
Atividade para praticar Git (branches/merge) e publicação no GitHub.

## Como executar
node app.js 10 20 30
# ou
npm start -- 10 20 30
EOF
```

### **.gitignore**
```bash
cat > .gitignore << 'EOF'
node_modules/
.env
.DS_Store
EOF
```

### **package.json**
```bash
cat > package.json << 'EOF'
{
  "name": "js-contador",
  "version": "1.0.0",
  "description": "Projeto de prática: Git + JS + GitHub",
  "main": "app.js",
  "scripts": {
    "start": "node app.js"
  },
  "license": "MIT"
}
EOF
```

### **app.js**
```bash
cat > app.js << 'EOF'
// Executar: node app.js 10 20 30

function ehNumeroValido(n) {
  return !Number.isNaN(n) && Number.isFinite(n);
}

function somaNumeros(valores) {
  let total = 0;
  for (let i = 0; i < valores.length; i++) {
    const n = Number(valores[i]);
    if (!ehNumeroValido(n)) {
      console.log(`Valor ignorado (não numérico): "${valores[i]}"`);
      continue;
    }
    total += n;
  }
  return total;
}

function resumo(valores) {
  const quantidade = valores.length;
  const convertidos = valores.map(Number).filter(ehNumeroValido);
  const soma = convertidos.reduce((acc, n) => acc + n, 0);
  const media = convertidos.length > 0 ? soma / convertidos.length : 0;

  console.log("=== RESUMO ===");
  console.log(`Quantidade de argumentos: ${quantidade}`);
  console.log(`Válidos: ${convertidos.length}`);
  console.log(`Soma: ${soma}`);
  console.log(`Média: ${media}`);
  if (convertidos.length === 0) {
    console.log("Dica: passe números como argumentos. Ex: node app.js 10 20 30");
  }
}

const args = process.argv.slice(2);
if (args.length === 0) {
  console.log("Nenhum número informado. Ex: node app.js 10 20 30");
} else {
  const total = somaNumeros(args);
  console.log(`Total calculado: ${total}`);
}
resumo(args);
EOF
```

### **Teste rápido**
```bash
node app.js 5 15 teste 20
```

---

## 🧱 Etapa 3 – Primeiro commit
```bash
git add .
git commit -m "chore: projeto inicial com app.js e docs"
git branch -M main
```

---

## 🌿 Etapa 4 – Criar branch, alterar e mesclar

### Criar branch de feature
```bash
git switch -c feature/mensagem-final
```

### Adicionar mensagem final
```bash
echo 'console.log("Obrigado por usar o js-contador!");' >> app.js
git add app.js
git commit -m "feat: mensagem final de agradecimento"
```

### Voltar à main e fazer merge
```bash
git switch main
git merge --no-ff feature/mensagem-final -m "merge: incorpora mensagem final"
```

> Se houver conflitos, resolva, depois:  
> `git add . && git commit -m "fix: resolve conflitos de merge"`

---

## ☁️ Etapa 5 – Publicar no GitHub (SSH)

1. Crie no GitHub um repositório **js-contador** (sem README).
2. Adicione o remoto e envie os commits:

```bash
git remote add origin git@github.com:seu-usuario/js-contador.git
git push -u origin main
git push -u origin feature/mensagem-final
```

### Verificar conexão SSH
```bash
ssh -T git@github.com
```

---

## 🔀 Etapa 6 – (Opcional) Pull Request
No GitHub, crie um **PR** de `feature/mensagem-final` → `main`  
Depois, faça o merge pela interface web.

---

## ✅ Etapa 7 – Validação final

```bash
npm start -- 2 4 6 X
git log --oneline --graph --decorate --all
```

---

## 📦 Entregáveis

- Link do repositório GitHub  
- Capturas de tela de:
  - Execução do `node app.js …`
  - Saída do `git log --oneline --graph --decorate --all`
  - Página do Pull Request (opcional)

---

## 🧮 Critérios de Avaliação

| Critério | Peso | Descrição |
|-----------|-------|-----------|
| **Git** | 30% | init, commits claros, `.gitignore`, histórico limpo |
| **Branches/Merge** | 20% | criação de feature, merge bem estruturado |
| **Código JS** | 30% | funcionamento correto, uso de funções e validação |
| **GitHub** | 20% | push via SSH, PR criado (opcional) |

---

## 💡 Desafios Opcionais

- Criar um script `npm run test` para validar a saída.  
- Adicionar um **GitHub Action** que rode `node app.js 1 2 3` a cada push.  
- Criar uma **tag e release**:
  ```bash
  git tag v1.0.0
  git push origin v1.0.0
  ```

---

## 🧰 Dicas rápidas

- Verifique o Node:
  ```bash
  node -v
  ```
- Cheque o Git:
  ```bash
  git --version
  ```
- Se o SSH falhar:
  ```bash
  ssh-add ~/.ssh/id_rsa
  ```

---

📅 **Tempo estimado:** 60 a 90 minutos  
👨‍💻 **Nível:** Iniciante a Intermediário  
🏁 **Resultado final:** Projeto JavaScript funcional publicado no GitHub com histórico Git completo.
