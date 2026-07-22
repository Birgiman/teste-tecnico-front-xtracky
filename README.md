# Teste Técnico - Desenvolvedor Front-end Júnior (React + TypeScript)

## Objetivo

O objetivo deste teste **não é avaliar se você sabe decorar APIs do React ou utilizar uma biblioteca específica**.

Queremos entender como você pensa, como organiza seu código, como estrutura uma aplicação e como resolve problemas do dia a dia de um desenvolvedor Front-end.

O uso de IA (ChatGPT, Claude, Copilot, Cursor, etc.) é permitido. Entretanto, durante a entrevista técnica, você deverá explicar todas as decisões tomadas no projeto. Portanto, utilize essas ferramentas apenas como apoio.

---

# Stack obrigatória

- React
- Vite
- TypeScript

Você pode utilizar bibliotecas auxiliares quando fizer sentido (React Router, React Hook Form, Zod, TanStack Query, etc.), mas procure justificar sua escolha.

---

# Cenário

Existe uma API (mock) que retorna uma lista de usuários.

O projeto já possui um arquivo JSON (`db.json`) contendo 100 registros.

Cada usuário possui a seguinte estrutura:

```ts
interface User {
  id: string;
  name: string;
  email: string;
  phone: string;
  description: string;
  createdAt: string;
}
```

Considere este JSON como sendo uma API REST.

---

# Como rodar a API mock

O JSON é servido como uma **API REST real** através do [json-server](https://github.com/typicode/json-server), já configurado via Docker. Você não precisa ter Node/npm instalado para rodar a API — apenas Docker.

Para subir a API:

```bash
docker compose up
```

A API ficará disponível em `http://localhost:3001`.

Endpoints principais:

- `GET /users` — lista todos os usuários
- `GET /users/:id` — detalhes de um usuário
- `POST /users` — cria um novo usuário
- `PUT /users/:id` / `PATCH /users/:id` — edita um usuário

> A API também suporta busca, ordenação e paginação nativas do json-server
> (ex.: `GET /users?q=maria`, `GET /users?_sort=name&_order=asc`, `GET /users?_page=1&_limit=10`).
> Fica a seu critério decidir o que resolver via API e o que resolver no Front-end.

---

# Desafio

Desenvolva uma pequena aplicação para gerenciamento desses usuários.

A aplicação deverá permitir:

- Listar usuários
- Buscar por nome
- Ordenar por nome
- Ordenar por data de criação
- Criar um novo usuário
- Editar um usuário existente
- Visualizar detalhes do usuário

Não é necessário implementar exclusão.

---

# Requisitos obrigatórios

## Listagem

- Exibir todos os usuários.
- Exibir estado de carregamento (Loading ou Skeleton).
- Exibir mensagem amigável caso ocorra erro.
- Exibir mensagem quando não houver resultados.

---

## Busca

Implementar busca por nome.

A busca deve atualizar a lista de forma eficiente.

---

## Ordenação

Permitir ordenação por:

- Nome
- Data de criação

---

## Cadastro

Criar formulário para cadastro.

Validar minimamente:

- Nome obrigatório
- Email válido
- Telefone válido

As validações podem ocorrer no Front-end.

---

## Edição

Permitir editar um usuário existente.

---

## Persistência

Persistir no Local Storage:

- Tema (Light/Dark)
- Último filtro utilizado

---

## Tema

Implementar:

- Light Theme
- Dark Theme

Persistindo a escolha do usuário.

---

## Tratamento de erro

Considere que a API pode falhar.

Sua aplicação não deve quebrar.

Exiba uma mensagem amigável ao usuário.

---

## Responsividade

A aplicação deve funcionar em desktop e dispositivos móveis.

Não é necessário criar um layout complexo.

---

# Arquitetura

Este é um dos pontos mais importantes da avaliação.

Esperamos um projeto desacoplado, organizado e de fácil manutenção.

Evite componentes gigantes responsáveis por toda a aplicação.

Exemplo esperado:

```
App

├── pages
│   ├── Users
│   └── UserDetails
│
├── components
│   ├── Header
│   ├── SearchInput
│   ├── UserCard
│   ├── UserList
│   └── ThemeSwitcher
│
├── hooks
│
├── services
│
├── utils
│
├── types
│
└── mocks
```

Essa estrutura é apenas uma sugestão.

---

# Desacoplamento

Este é um dos principais critérios de avaliação.

Sempre que possível:

- Componentes devem possuir apenas uma responsabilidade.
- Evite lógica de negócio diretamente na interface.
- Evite duplicação de código.
- Crie funções reutilizáveis.
- Separe responsabilidades.
- Evite componentes excessivamente grandes.
- Pense sempre em reutilização.

Um componente deve existir porque ele possui uma responsabilidade clara, e não apenas porque "funciona".

---

# Contratos

Considere que você está desenvolvendo o Front-end antes do Back-end.

Sempre que necessário, defina claramente os contratos que seriam enviados para a API.

Exemplo:

## POST /users

```json
{
  "name": "John Doe",
  "email": "john@email.com",
  "phone": "(11) 99999-9999",
  "description": "Lorem ipsum"
}
```

Pense em como esses contratos poderiam evoluir futuramente.

---

# O que será avaliado

## Organização

- Organização do projeto
- Estrutura de pastas
- Legibilidade
- Nomeação

---

## Componentização

- Componentes reutilizáveis
- Responsabilidade única
- Desacoplamento

---

## React

- Hooks
- Estado
- Effects
- Renderização
- Performance

---

## TypeScript

- Tipagem
- Interfaces
- Organização dos tipos

---

## Código

- Clareza
- Simplicidade
- Reutilização
- Boas práticas

---

## UX

- Loading
- Estados vazios
- Tratamento de erro
- Responsividade

---

# README

Inclua um README contendo:

- Como executar o projeto
- Decisões técnicas tomadas
- Bibliotecas utilizadas
- Justificativa das escolhas
- O que faria se tivesse mais tempo

---

# Pull Request

Abra um Pull Request contendo uma breve descrição:

- O que foi desenvolvido
- Principais decisões
- Dificuldades encontradas
- Possíveis melhorias

---

# Durante a entrevista técnica

O código será revisado junto com você.

O objetivo não é encontrar erros, mas entender seu processo de desenvolvimento e suas decisões técnicas.

Algumas perguntas poderão ser feitas durante essa conversa.

---

Boa sorte!