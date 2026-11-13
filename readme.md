<div align="center">

# 🛒 API de Produtos com MongoDB

**API REST leve e prática desenvolvida em Node.js com Express para gerenciamento de produtos no MongoDB.**

[![Node.js](https://shields.io)](https://nodejs.org)
[![Express.js](https://shields.io)](https://expressjs.com)
[![MongoDB](https://shields.io)](https://mongodb.com)
[![License](https://shields.io)](#-licença)

</div>

---

## 📋 Visão Geral

Este projeto oferece operações completas de **CRUD** (Create, Read, Update, Delete) para a coleção `produtos` dentro do banco de dados `loja`. Ele foi estruturado para demonstrar, de forma simples e direta, a integração entre **Node.js**, **Express** e o **driver oficial do MongoDB**.

---

## 🚀 Tecnologias Utilizadas

* **[Node.js](https://nodejs.org)** — Ambiente de execução JavaScript no servidor
* **[Express](https://expressjs.com)** — Framework web rápido e minimalista para criação de rotas
* **[MongoDB Node.js Driver](https://mongodb.comdocs/drivers/node/current/)** — Driver oficial para conexão e manipulação de dados no MongoDB

---

## 📁 Estrutura do Projeto

```text
api-mongo-node/
├── 📄 index.js          # Ponto de entrada e rotas da API
├── 📦 package.json      # Dependências e scripts do projeto
├── 📝 README.md         # Documentação do projeto
└── 📂 node_modules/     # Módulos instalados via npm
```

---

## ⚙️ Pré-requisitos

Antes de começar, certifique-se de ter instalado em sua máquina:

* **[Node.js](https://nodejs.org)** (versão LTS recomendada)
* **[npm](https://npmjs.com)** (geralmente instalado junto com o Node.js)
* **[MongoDB](https://mongodb.com)** em execução localmente ou via serviço em nuvem (ex: MongoDB Atlas)

---

## 🔧 Instalação e Configuração

### 1. Clonar e instalar dependências

```bash
# Clone este repositório
git clone <URL_DO_REPOSITORIO>

# Acesse a pasta do projeto
cd api-mongo-node

# Instale as dependências
npm install
```

### 2. Configurar variáveis de ambiente

A aplicação utiliza a variável `MONGO_URI` para realizar a conexão com o banco de dados. Defina-a no seu terminal antes de iniciar:

* **Windows (PowerShell):**
  ```powershell
  \$env:MONGO_URI = "mongodb://localhost:27017"
  ```

* **Linux / macOS:**
  ```bash
  export MONGO_URI="mongodb://localhost:27017"
  ```

> 💡 **Nota:** Por padrão, a aplicação conecta-se ao banco de dados **`loja`** e manipula a coleção **`produtos`**.

---

## ▶️ Execução

Inicie o servidor com o comando:

```bash
node index.js
```

Se tudo ocorrer bem, a API estará disponível em:
🔗 `http://localhost:3000`

---

## 📌 Endpoints da API

| Método | Endpoint | Descrição |
| :---: | :--- | :--- |
| ![POST](https://shields.io) | `/produtos` | Cria um novo produto |
| ![GET](https://shields.io) | `/produtos` | Lista todos os produtos cadastrados |
| ![GET](https://shields.io) | `/produtos/:id` | Busca um produto específico pelo ID |
| ![PUT](https://shields.io) | `/produtos/:id` | Atualiza os dados de um produto |
| ![DELETE](https://shields.io) | `/produtos/:id` | Remove um produto do banco |

---

## 🧪 Exemplos de Uso (cURL)

<details>
<summary><b>1. Criar um produto (POST)</b></summary>

```bash
curl -X POST http://localhost:3000/produtos \
  -H "Content-Type: application/json" \
  -d '{
    "nome": "Teclado",
    "preco": 99.9
  }'
```
</details>

<details>
<summary><b>2. Listar todos os produtos (GET)</b></summary>

```bash
curl http://localhost:3000/produtos
```
</details>

<details>
<summary><b>3. Buscar produto por ID (GET)</b></summary>

```bash
curl http://localhost:3000/produtos/ID_DO_PRODUTO
```
</details>

<details>
<summary><b>4. Atualizar um produto (PUT)</b></summary>

```bash
curl -X PUT http://localhost:3000/produtos/ID_DO_PRODUTO \
  -H "Content-Type: application/json" \
  -d '{
    "preco": 109.9
  }'
```
</details>

<details>
<summary><b>5. Deletar um produto (DELETE)</b></summary>

```bash
curl -X DELETE http://localhost:3000/produtos/ID_DO_PRODUTO
```
</details>

---

## 🗄️ Estrutura do Documento no MongoDB

Os registros na coleção `produtos` seguem o formato JSON abaixo:

```json
{
  "_id": "64f7c9d123abc123def4567",
  "nome": "Teclado",
  "preco": 99.9
}
```

---

## ⚠️ Observações e Boas Práticas

* **Uso recomendado:** Ideal para fins de estudo, provas de conceito (PoCs) e pequenos cadastros.
* **Ambiente de produção:** Caso decida evoluir este projeto para produção, recomenda-se implementar:
  * Validação de dados de entrada (ex: `Joi` ou `Zod`);
  * Autenticação e autorização (ex: `JWT`);
  * Tratamento centralizado de erros;
  * Gerenciamento de variáveis de ambiente com `dotenv`.

---

## 📄 Licença

Este projeto está disponível livremente para fins de **estudo e desenvolvimento**.
