# Todolist — React + Fastify + MySQL

Sistema de lista de tarefas com a interface das imagens de referência (tema escuro, logo "to*do.*", busca, contadores e modal de criação).

## Estrutura

```
todolist/
├── backend/     # API em Fastify + MySQL
└── frontend/    # Interface em React (Vite + Tailwind)
```

## 1. Banco de dados (MySQL)

Crie o banco e a tabela executando o script:

```bash
C:\xampp\mysql\bin\mysql -u root -p < backend/schema.sql
```

(O backend também cria a tabela automaticamente ao iniciar, caso ainda não exista.)

## 2. REST Client (Extensão)

Baixe a extensão REST Client no vscode

## 2. Backend (Fastify)

```bash
cd backend
copy .env.example .env
# edite o .env com usuário/senha do seu MySQL
npm install
npm run dev
```

A API sobe em `http://localhost:3333`.

### Endpoints

| Método | Rota               | Descrição                                   |
| ------ | ------------------ | ------------------------------------------- |
| GET    | /api/tasks?search= | Lista tarefas (com busca opcional)          |
| POST   | /api/tasks         | Cria tarefa `{ title, dueDate? }`           |
| PATCH  | /api/tasks/:id     | Atualiza `{ completed?, title?, dueDate? }` |
| DELETE | /api/tasks/:id     | Remove uma tarefa                           |

Acesse o documento rotas.http e teste o send request