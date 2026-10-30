# API MongoDB - Produtos

Uma API REST simples para gerenciar produtos usando Node.js, Express e MongoDB.

## Pré-requisitos

- Node.js instalado
- Acesso a um banco MongoDB

## Configuração

Instale as dependências do projeto:

```bash
npm install
```

Defina a variável de ambiente `MONGO_URI` com a URI do seu MongoDB.

Exemplo no PowerShell:

```powershell
$env:MONGO_URI = "mongodb://localhost:27017"
```

## Executar

```bash
node index.js
```

O servidor inicia na porta `3000`. A aplicação usa o banco `loja` e a coleção `produtos`.

## Rotas disponíveis

| Método | Endpoint | Ação |
|---|---|---|
| POST | `/produtos` | Cria um produto |
| GET | `/produtos` | Retorna todos os produtos |
| GET | `/produtos/:id` | Retorna um produto pelo ID |
| PUT | `/produtos/:id` | Atualiza um produto |
| DELETE | `/produtos/:id` | Exclui um produto |

### Criar produto

Envie um JSON no corpo da requisição:

```json
{
  "nome": "Teclado",
  "preco": 99.9
}
```

Exemplo com `curl`:

```bash
curl -X POST http://localhost:3000/produtos -H "Content-Type: application/json" -d "{\"nome\":\"Teclado\",\"preco\":99.9}"
```

### Listar produtos

```bash
curl http://localhost:3000/produtos
```

### Consultar, atualizar ou excluir

Substitua `ID_DO_PRODUTO` por um `_id` válido retornado pelo MongoDB.

```bash
curl http://localhost:3000/produtos/ID_DO_PRODUTO
```

```bash
curl -X PUT http://localhost:3000/produtos/ID_DO_PRODUTO -H "Content-Type: application/json" -d "{\"preco\":109.9}"
```

```bash
curl -X DELETE http://localhost:3000/produtos/ID_DO_PRODUTO
```
