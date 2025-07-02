# 💸 GoFinance API

Esta é uma API RESTful desenvolvida com **Node.js** e **PostgreSQL** para gerenciar transações financeiras, como entradas e saídas. O projeto faz parte de um sistema integrado com front-end, permitindo o cadastro e a listagem de movimentações financeiras.

---

## 🚀 Tecnologias Utilizadas

- [Node.js](https://nodejs.org/)
- [Express.js](https://expressjs.com/)
- [PostgreSQL](https://www.postgresql.org/)
- [dotenv](https://www.npmjs.com/package/dotenv)
- [cors](https://www.npmjs.com/package/cors)

---

## 📦 Instalação

```bash
git clone https://github.com/seu-usuario/seu-repositorio.git
cd seu-repositorio
npm install
```

---

## 🔧 Configuração do Banco de Dados

1. Crie um banco no PostgreSQL com o nome:

```sql
CREATE DATABASE transacoes_db;
```

2. Crie a tabela de transações:

```sql
CREATE TABLE transacoes (
  id SERIAL PRIMARY KEY,
  titulo TEXT NOT NULL,
  preco NUMERIC NOT NULL,
  categoria TEXT NOT NULL,
  data DATE NOT NULL,
  tipo TEXT CHECK (tipo IN ('entrada', 'saida')) NOT NULL
);
```

3. Configure seu arquivo `.env` com os dados do banco:

```env
DB_USER=postgres
DB_PASSWORD=admin
DB_HOST=localhost
DB_PORT=5432
DB_DATABASE=transacoes_db
```

---

## ▶️ Executando a API

```bash
node app.js
```

A API estará disponível em:  
📍 **http://localhost:3000/api/v1/transacoes**

---

## 📚 Endpoints

### 🔹 `GET /api/v1/transacoes`

Retorna a lista de todas as transações cadastradas.

**Resposta:**

```json
[
  {
    "id": 1,
    "titulo": "Salário",
    "preco": 5000,
    "categoria": "Trabalho",
    "data": "2025-07-01",
    "tipo": "entrada"
  }
]
```

---

### 🔹 `POST /api/v1/transacoes`

Cadastra uma nova transação.

**Exemplo de body JSON:**

```json
{
  "titulo": "Conta de Luz",
  "preco": 150.75,
  "categoria": "Contas",
  "data": "2025-07-02",
  "tipo": "saida"
}
```

**Resposta esperada:**

```json
{
  "id": 2,
  "titulo": "Conta de Luz",
  "preco": 150.75,
  "categoria": "Contas",
  "data": "2025-07-02",
  "tipo": "saida"
}
```

---

## 🧠 Organização do Projeto

```bash
├── app.js
├── db.js
├── .env
├── controllers
│   └── transacoesController.js
├── routes
│   ├── index.js
│   └── transacoes.js
```

---

## 📝 Licença

Este projeto está sob a licença MIT.

---

## 👨‍💻 Autor

Desenvolvido por **Layan Gabriel**  


---
