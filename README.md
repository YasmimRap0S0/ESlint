# 🧩 ESLint — Guia Prático

## 📌 Categoria: Onde entra o ESLint?

O ESLint é uma ferramenta de **análise estática de código**, que **contribui** para os **testes não funcionais** — aqueles que avaliam aspectos como segurança, desempenho e qualidade interna **sem executar o sistema**. Ele analisa seu código JavaScript (incluindo React) em busca de:

- ❌ **Erros de sintaxe**
- 🎯 **Más práticas de programação**
- 📐 **Problemas de estilo e formatação**
- 🔒 **Riscos que afetam segurança ou legibilidade**

### 🔧 Contribuições do ESLint por categoria:

| Categoria | Papel do ESLint                                                                 |
|----------------------------------|----------------------------------------------------------------------------------|
| **Manutenibilidade**             | Garante código limpo, padronizado e fácil de manter                             |
| **Reusabilidade**                | Estimula boas práticas que facilitam reaproveitamento de componentes            |
| **Segurança** (com plugins)      | Pode detectar padrões inseguros no código, como uso indevido de funções         |
| **Qualidade interna**            | Aponta problemas que afetam organização, legibilidade e consistência do código  |

> 💬 **Resumo prático**: O ESLint não testa se o programa *funciona*, ele lê seu código e avalia se está *bem feito* e *aponta problemas*.

---

## 📦 Instalação

No terminal, dentro da pasta do seu projeto frontend:

```bash
npm install eslint --save-dev
```

---

## ⚙️ Configuração Básica

Crie um arquivo chamado `.eslintrc.js` dentro da pasta `frontend/src` com esta configuração:

```javascript
module.exports = {
  env: {
    browser: true,
    es2021: true,
  },
  extends: ['eslint:recommended', 'plugin:react/recommended'],
  parserOptions: {
    ecmaFeatures: {
      jsx: true,
    },
    ecmaVersion: 12,
    sourceType: 'module',
  },
  plugins: ['react'],
  rules: {
    'no-console': 'off',
  },
};
```

---

## 🧩 Explicação detalhada das opções

### 🔹 `env`
Define onde o código será usado:
- `browser: true` → permite usar `window`, `document`, etc.
- `es2021: true` → habilita recursos modernos do JavaScript como `Promise.any`, `??`, `replaceAll`.

### 🔹 `extends`
Importa conjuntos de regras já validadas:
- `'eslint:recommended'` → boas práticas genéricas de JavaScript.
- `'plugin:react/recommended'` → regras específicas para projetos React.

### 🔹 `parserOptions`
Indica como o ESLint deve interpretar o código:
- `jsx: true` → permite trabalhar com JSX (`<div>Hello</div>`).
- `ecmaVersion: 12` → compatível com ECMAScript 2021.
- `sourceType: 'module'` → habilita `import/export`.

### 🔹 `plugins`
Adiciona funcionalidades extras:
- `'react'` → habilita regras de verificação para componentes React, como `props`, `hooks`, etc.

### 🔹 `rules`
Define ou modifica regras específicas:
- `'no-console': 'off'` → permite usar `console.log()` sem avisos.

Você pode incluir outras:
```javascript
'quotes': ['error', 'single'], // exige aspas simples
'semi': ['error', 'always'],   // exige ponto e vírgula
```

---

## 🧪 Como usar na prática

### Para gerar relatório HTML:
```bash
 npx eslint src/ -f html -o eslint-report.html
```

---

| 🧩 Parte do comando        | 📝 Significado                                                                 |
|----------------------------|--------------------------------------------------------------------------------|
| `npx`                      | Executa pacotes diretamente sem instalar globalmente                          |
| `eslint`                   | Invoca o ESLint para analisar o código                                        |
| `src/`                     | Pasta que será varrida pelo ESLint                                            |
| `-f html`                  | Formato do relatório de saída será HTML                                       |
| `-o eslint-report.html`    | Nome do arquivo gerado com o relatório (salvo na raiz ou pasta atual do projeto) |

---

Abra o `eslint-report.html` no navegador para ver os alertas.

### Para corrigir:

```bash
npx eslint src/ --fix

```
---

## ✅ Conclusão

O ESLint é essencial para garantir:

- Padronização de código
- Facilidade de manutenção
- Prevenção de bugs ocultos
- Maior colaboração em equipe

---

## Links para aprofundar
- [Documentação oficial traduzida](https://pt-br.eslint.org/)
- [Instalando e Configurando ESLint | Tutorial Definitivo (2024)](https://www.youtube.com/watch?v=JgEszvVTe5g)
- [Configurando ESLint: Alura](https://www.alura.com.br/conteudo/eslint-padronizando-codigo-regras-personalizadas)
