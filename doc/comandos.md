### iniciar projeto

- `yarn create react-app . --template typescript --strict`

### instalação de dependências

- `yarn add -D eslint @typescript-eslint/parser @typescript-eslint/eslint-plugin eslint-plugin-prettier eslint-config-prettier`

### configurar o prettier

- Crie um arquivo .prettierrc na raiz do projeto
- Adicione o seguinte conteúdo:

```json
{
  "semi": true,
  "singleQuote": true,
  "trailingComma": "all",
  "tabWidth": 2,
  "endOfLine": "auto"
}
```

### configuração do eslint

- Crie um arquivo eslint.config.js na raiz do projeto
- Adicione o seguinte conteúdo:

```js
import js from '@eslint/js';
import * as tseslint from '@typescript-eslint/eslint-plugin';
import tsparser from '@typescript-eslint/parser';
import prettierConfig from 'eslint-config-prettier';
import jest from 'eslint-plugin-jest';
import prettier from 'eslint-plugin-prettier';

// Define as variáveis globais do navegador
const browserGlobals = {
  document: 'readonly',
  HTMLElement: 'readonly',
  window: 'readonly',
  navigator: 'readonly',
  JSX: 'readonly',
  jest: 'readonly',
  // Adicione outras variáveis globais do navegador conforme necessário
};

export default [
  // Configurações recomendadas do ESLint
  js.configs.recommended,
  //...require('@eslint/js').configs.recommended,

  // Configuração do Prettier para desativar regras conflitantes
  prettierConfig,

  {
    ...jest.configs['flat/recommended'],
    ...jest.configs['flat/style'],

    files: ['**/*.{js,jsx,ts,tsx}', 'test/**', '**/*.spec.js', '**/*.test.js'],
    languageOptions: {
      parser: tsparser,
      parserOptions: {
        ecmaVersion: 'latest',
        sourceType: 'module',
        jsx: true, // Habilita parsing de JSX
      },

      globals: {
        ...browserGlobals,
        ...jest.environments.globals.globals,
        jest: true, // Define a variável global "jest" como
      }, // Define as variáveis globais
    },

    plugins: {
      '@typescript-eslint': tseslint,
      prettier: prettier,
      eslint: js,
      jest: jest,
    },
    rules: {
      // Regras básicas do TypeScript
      '@typescript-eslint/explicit-function-return-type': 'error',
      '@typescript-eslint/no-explicit-any': 'error',
      '@typescript-eslint/no-unused-vars': 'error',

      // Regras do jest
      'jest/prefer-expect-assertions': 'off',
      ...jest.configs['flat/recommended'].rules,
      'jest/no-disabled-tests': 'warn',
      'jest/no-focused-tests': 'error',
      'jest/no-identical-title': 'error',
      'jest/prefer-to-have-length': 'warn',
      'jest/valid-expect': 'error',

      // Regras do Prettier
      'prettier/prettier': [
        'error',
        {
          singleQuote: true,
          semi: true,
          trailingComma: 'all',
          tabWidth: 2,
          endOfLine: 'auto',
        },
      ],
    },
    settings: {
      'import/resolver': {
        typescript: true,
        node: true,
      },
    },
  },
];
```

- Adicione ao package.json:

```json
{
  "type": "module",
  "scripts": {
    "lint": "eslint . --fix"
  }
}
```

- Execute o lint com: `yarn lint`
