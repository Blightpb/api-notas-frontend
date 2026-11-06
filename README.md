# Notas (Front-end)

Aplicação web para gerenciar notas, com operações completas de **CRUD** (criar, visualizar, editar e excluir). Ela consome a API REST de notas desenvolvida com Express.js, que grava os dados em um arquivo JSON.

Este projeto é o front-end da atividade. O código do back-end está em outro repositório (veja a seção **Links**).

## Links

- **Aplicação online (Vercel):** https://SUA-URL.vercel.app
- **Repositório do back-end:** https://github.com/SEU_USUARIO/api-notas-backend
- **API online (Render):** https://SUA-URL.onrender.com/api/notes

> Observação: o back-end usa o plano gratuito do Render, que suspende o serviço após um período sem uso. Se a lista de notas demorar a aparecer, aguarde cerca de 1 minuto e recarregue a página.

## Funcionalidades

- **Listar** todas as notas salvas
- **Criar** uma nova nota com título e texto
- **Editar** uma nota existente
- **Excluir** uma nota, com confirmação
- Exibição da data e hora de criação de cada nota
- Proteção contra HTML digitado nos campos, que é exibido como texto

## Tecnologias

- HTML5
- CSS3
- JavaScript puro (Fetch API, `async/await`)
- Vercel (deploy)

## Estrutura do projeto

```
notas-frontend/
├── index.html    # página, estilos e lógica da aplicação
└── README.md
```

## Como executar localmente

Não é preciso instalar nada.

```bash
# 1. clonar o repositório
git clone https://github.com/SEU_USUARIO/notas-frontend.git
cd notas-frontend
```

2. Abra o arquivo `index.html` no navegador (dois cliques sobre ele).

Por padrão, a aplicação usa a API publicada no Render.

### Usando o back-end local

Para testar com o back-end rodando no seu computador:

1. Inicie a API (`npm start` na pasta do back-end).
2. No `index.html`, altere a constante `API`:

```js
const API = 'http://localhost:3000/api/notes';
```

Lembre-se de voltar para a URL do Render antes de publicar.

## Integração com a API

| Operação | Método | Rota |
|---|---|---|
| Listar notas | GET | `/api/notes` |
| Criar nota | POST | `/api/notes` |
| Editar nota | PUT | `/api/notes/:id` |
| Excluir nota | DELETE | `/api/notes/:id` |

Corpo enviado ao criar ou editar:

```json
{
  "titulo": "Título da nota",
  "texto": "Conteúdo da nota"
}
```

## Como usar

1. Preencha **Título** e **Texto** e clique em **Adicionar**.
2. A nota aparece na lista abaixo.
3. Clique em **Editar** para carregar a nota nos campos, altere o que quiser e clique em **Salvar alterações**. Para desistir, clique em **Cancelar edição**.
4. Clique em **Excluir** e confirme para remover a nota.

## Deploy na Vercel

1. Importar este repositório como novo projeto na Vercel.
2. **Framework Preset:** Other
3. Deixar os campos de build vazios e clicar em **Deploy**.
