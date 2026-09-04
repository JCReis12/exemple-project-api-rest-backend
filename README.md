# Backend - API de Notas

API REST simples para criar, listar, editar e excluir notas. Os dados são armazenados no arquivo `data.json`.

## Pré-requisitos

- Node.js instalado
- npm instalado

## Instalação

No terminal, entre na pasta do backend e instale as dependências:

```bash
cd backend
npm install
```

## Como executar

Para iniciar o servidor normalmente:

```bash
npm start
```

Para executar em modo de desenvolvimento, reiniciando automaticamente após alterações:

```bash
npm run dev
```

O servidor ficará disponível em:

```text
http://localhost:3000
```

## Rotas da API

| Método | Rota | Descrição |
| --- | --- | --- |
| `GET` | `/api/notes` | Lista todas as notas |
| `POST` | `/api/notes` | Cria uma nova nota |
| `PUT` | `/api/notes/:id` | Atualiza uma nota |
| `DELETE` | `/api/notes/:id` | Exclui uma nota |

### Criar uma nota

Envie um JSON com `titulo` e `texto`:

```json
{
	"titulo": "Minha nota",
	"texto": "Conteúdo da nota"
}
```

Exemplo com `curl`:

```bash
curl -X POST http://localhost:3000/api/notes \
	-H "Content-Type: application/json" \
	-d "{\"titulo\":\"Minha nota\",\"texto\":\"Conteúdo da nota\"}"
```

### Atualizar uma nota

Substitua `ID_DA_NOTA` pelo `id` retornado ao criar ou listar uma nota:

```bash
curl -X PUT http://localhost:3000/api/notes/ID_DA_NOTA \
	-H "Content-Type: application/json" \
	-d "{\"titulo\":\"Título atualizado\",\"texto\":\"Texto atualizado\"}"
```

### Excluir uma nota

```bash
curl -X DELETE http://localhost:3000/api/notes/ID_DA_NOTA
```

## Observações

- A API permite requisições de diferentes origens por meio do CORS.
- As notas são persistidas localmente em `data.json`.
- A porta padrão é `3000` e está definida em `server.js`.
