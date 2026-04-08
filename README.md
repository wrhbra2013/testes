# CodeTrain

Plataforma de Treinamento em Programação com exercícios interativos para múltiplas linguagens.

## Funcionalidades

- 5 linguagens de programação (JavaScript, Python, Java, C++, Go)
- 75 exercícios práticos com diferentes níveis de dificuldade
- Dashboard de progresso com gráficos
- Sistema de conquistas
- Editor de código com tela cheia
- Execução sandboxed de código JavaScript

## Começando

### Instalação

```bash
npm install
```

### Execução

Abra `index.html` diretamente no navegador ou use um servidor local:

```bash
npx serve .
# ou
python -m http.server 8000
```

## Scripts Disponíveis

| Script             | Descrição                                 |
| ------------------ | ----------------------------------------- |
| `npm run lint`     | Verifica código com ESLint                |
| `npm run lint:fix` | Corrige automaticamente problemas de lint |
| `npm run format`   | Formata código com Prettier               |
| `npm run test`     | Executa testes (placeholder)              |

## Arquitetura

```
codetrain/
├── index.html           # Página principal
├── static/
│   ├── css/
│   │   └── training.css # Estilos da aplicação
│   └── js/
│       └── training.js  # Lógica da aplicação
├── .eslintrc.json      # Configuração ESLint
├── .prettierrc         # Configuração Prettier
└── package.json        # Dependências e scripts
```

## Segurança

- Código JavaScript executado em **iframe sandboxed** (`sandbox="allow-scripts"`)
- Sem dependências externas (zero vulnerabilidades de pacotes)
- Dados armazenados apenas em localStorage local

## Testes

O projeto usa **Vitest** para testes unitários:

```bash
npm install vitest
npm test
```

### Escrevendo Testes

```javascript
import { describe, it, expect } from 'vitest';

describe('App', () => {
    it('deve inicializar corretamente', () => {
        expect(App).toBeDefined();
    });
});
```

## Contribuindo

1. Fork o repositório
2. Crie uma branch (`git checkout -b feature/nova-funcionalidade`)
3. Commit suas mudanças (`git commit -m 'Adiciona nova funcionalidade'`)
4. Push para a branch (`git push origin feature/nova-funcionalidade`)
5. Abra um Pull Request

## Licença

GNU General Public License v3.0 - veja [LICENSE](LICENSE)
