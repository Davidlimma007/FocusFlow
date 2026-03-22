# Focus Flow

## 1. Visão Geral

O **Focus Flow** é uma aplicação de gerenciamento de tarefas orientada à priorização inteligente. O objetivo é transformar listas estáticas de tarefas em um fluxo dinâmico, organizado por nível de prioridade, contexto e execução.

A proposta central é simples:

> **não apenas listar tarefas, mas guiar o usuário sobre o que fazer agora.**

---

## 2. Problema

Ferramentas tradicionais de To-Do List apresentam limitações:

* Listas extensas sem priorização clara
* Falta de direcionamento prático
* Sobrecarga cognitiva
* Dificuldade em decidir a próxima ação

---

## 3. Solução

O **Focus Flow** resolve isso através de:

* Classificação por **nível de prioridade**
* Organização em **fluxo de execução**
* Foco em **ação imediata (next task)**
* Estrutura pensada para produtividade real

---

## 4. Funcionalidades (MVP)

### CRUD de Tarefas

* Criar tarefa
* Listar tarefas (com paginação)
* Buscar tarefa por email
* Atualizar tarefa por email
* Deletar tarefa por email

### Estrutura da Tarefa

* `id` (UUID)
* `title`
* `description`
* `priority` (LOW, MEDIUM, HIGH)
* `email`
* `createdAt`
* `updatedAt`

### Regras de Negócio

* Prioridade influencia ordenação
* Email funciona como identificador lógico
* Listagens devem ser paginadas
* Respostas HTTP padronizadas

---

## 5. Stack Tecnológica

| Camada        | Tecnologia             |
| ------------- | ---------------------- |
| Backend       | Java + Spring Boot     |
| Build         | Maven / Gradle         |
| Banco         | PostgreSQL (ou H2 dev) |
| ORM           | Spring Data JPA        |
| API           | REST                   |
| Identificação | UUID                   |

---

## 6. Estrutura do Projeto

```
focus-flow/
│
├── src/main/java/com/focusflow/
│   ├── controller/
│   ├── service/
│   ├── repository/
│   ├── entity/
│   ├── dto/
│   └── config/
│
├── src/main/resources/
│   ├── application.yml
│
└── README.md
```

---

## 7. Endpoints

### Criar tarefa

```
POST /tasks
```

### Listar tarefas (paginado)

```
GET /tasks?page=0&size=10
```

### Buscar por email

```
GET /tasks/email/{email}
```

### Atualizar por email

```
PUT /tasks/email/{email}
```

### Deletar por email

```
DELETE /tasks/email/{email}
```

---

## 8. Padrão de Resposta HTTP

| Situação           | Código |
| ------------------ | ------ |
| Criado com sucesso | 201    |
| Sucesso            | 200    |
| Sem conteúdo       | 204    |
| Não encontrado     | 404    |
| Erro de validação  | 400    |
| Erro interno       | 500    |

---

## 9. Roadmap

### Fase 1 (Atual)

* CRUD completo
* Estrutura base
* API REST funcional

### Fase 2

* Sistema de ordenação inteligente
* Score dinâmico de prioridade
* Filtro por contexto

### Fase 3

* Interface frontend (Web/Mobile)
* Integração com notificações
* Insights de produtividade

---

## 10. Setup Local

### Pré-requisitos

* Java 21+
* Spring Boot 3+
* Maven
* Git

### Passos

---

## 11. Objetivo do Projeto

Mais do que um CRUD, o Focus Flow é um experimento em:

* **produtividade orientada por decisão**
* **priorização automatizada**
* **redução de fricção cognitiva**

---

## 12. Licença

Este projeto está sob a licença MIT.

---

## 13. Contribuição

Pull requests são bem-vindos. Para mudanças maiores:

1. Fork do projeto
2. Crie uma branch (`feature/nova-feature`)
3. Commit (`git commit -m 'feat: nova feature'`)
4. Push (`git push origin feature/nova-feature`)
5. Abra um PR

---

## 14. Status

🚧 Em desenvolvimento inicial (MVP)

---

