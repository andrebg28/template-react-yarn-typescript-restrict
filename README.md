# Template React + TypeScript (Strict Mode)

Template pré-configurado para projetos React com TypeScript em modo strict, incluindo configurações otimizadas de ESLint, Prettier e Jest.

## 🚀 Características

- ⚛️ React 18
- 📘 TypeScript em modo strict
- 🎨 Prettier para formatação consistente
- 🔍 ESLint configurado com regras rigorosas
- ✅ Jest para testes
- 📱 Configurações otimizadas para desenvolvimento web

## 📦 Configurações Incluídas

### Prettier (.prettierrc)

- Ponto e vírgula no final das declarações
- Aspas simples
- Vírgula ao final de objetos e arrays
- Indentação de 2 espaços
- Final de linha automático

### ESLint

- Integração com TypeScript
- Regras estritas de tipagem
- Configuração personalizada para Jest
- Integração com Prettier
- Variáveis globais do navegador pré-configuradas

### TypeScript

- Modo strict ativado
- Suporte completo a React
- Configurações otimizadas para desenvolvimento web
- Verificação rigorosa de tipos

## 🚀 Como Usar

1. Clique no botão "Use this template" no GitHub
2. Clone o repositório criado
3. Instale as dependências:

```bash
yarn install
```

4. Inicie o projeto:

```bash
yarn start
```

## 📜 Scripts Disponíveis

- `yarn start`: Inicia o projeto em modo de desenvolvimento
- `yarn build`: Cria a versão de produção
- `yarn test`: Executa os testes
- `yarn lint`: Executa o ESLint e corrige problemas automaticamente

## 🔧 Dependências Principais

- React 18.3.1
- TypeScript 4.4.2
- ESLint 9.16.0
- Prettier 3.4.1
- Jest (via react-scripts)

## 📝 Notas Importantes

- O projeto usa configurações estritas de TypeScript para garantir maior segurança de tipos
- ESLint está configurado para forçar boas práticas de desenvolvimento
- Prettier garante consistência no estilo de código
- Configuração completa para testes com Jest

## Estrutura do Projeto

O projeto segue uma estrutura padrão inicial de aplicações React:

```
my-react-ts-template/
├── public/
│   ├── index.html
│   └── favicon.ico
├── src/
│   ├── App.tsx
│   ├── index.tsx
│   ├── setupTests.ts
│   └── ...
├── .eslintrc.js
├── .prettierrc
├── .gitignore
├── package.json
├── tsconfig.json
└── README.md
```

## Configurações

### TypeScript

- Modo Estrito: Ativado no tsconfig.json.
- Target: ES5.
- Lib: DOM, DOM.Iterable, ESNext.
- Strict Mode: Ativado.
- Force Consistent Casing in File Names: Ativado.
- No Fallthrough Cases in Switch: Ativado.

### ESLint

- Regras Recomendadas: Configuradas para TypeScript e Jest.
- Plugins: @typescript-eslint, eslint-plugin-jest, eslint-plugin-prettier.

### Prettier

- Semi-colons: Ativados.
- Single Quotes: Ativados.
- Trailing Commas: Ativados.
- Tab Width: 2 espaços.
- End of Line: Automático.

Jest

- Ambiente: Node.
- Regras: Configuradas para melhorar a qualidade dos testes.

## 🤝 Contribuindo

Sinta-se à vontade para enviar pull requests com melhorias ou correções.

📄 Licença
Este projeto está sob a licença MIT.
