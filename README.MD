# 🏎️ Formula 1 API

API REST desenvolvida com **TypeScript** e **Fastify**, criada como projeto de estudo para praticar a construção de APIs utilizando Node.js.

O projeto disponibiliza informações sobre **equipes e pilotos de Fórmula 1**, além de demonstrar a configuração de **CORS**, criação de rotas e utilização de parâmetros dinâmicos.

## 🚀 Tecnologias

* **TypeScript**
* **Node.js**
* **Fastify**
* **@fastify/cors**

## 📌 Funcionalidades

A API possui endpoints para:

* Listar todas as equipes de Fórmula 1
* Listar todos os pilotos
* Buscar um piloto específico pelo ID
* Retornar erro `404` quando o piloto não é encontrado
* Configurar CORS para permitir requisições de diferentes origens
* Utilizar tipagem com TypeScript para os parâmetros das rotas

## 📂 Estrutura dos dados

### Teams

Cada equipe possui:

```json
{
  "id": 1,
  "name": "McLaren",
  "base": "Woking, United Kingdom"
}
```

### Drivers

Cada piloto possui:

```json
{
  "id": 1,
  "name": "Max Verstappen",
  "team": "Red Bull Racing"
}
```

## 🔗 Endpoints

### Listar equipes

```http
GET /teams
```

Retorna todas as equipes cadastradas.

### Listar pilotos

```http
GET /drivers
```

Retorna todos os pilotos cadastrados.

### Buscar piloto por ID

```http
GET /drivers/:id
```

Exemplo:

```http
GET /drivers/1
```

Resposta:

```json
{
  "driver": {
    "id": 1,
    "name": "Max Verstappen",
    "team": "Red Bull Racing"
  }
}
```

Caso o piloto não exista:

```json
{
  "message": "Driver not found"
}
```

Status HTTP:

```http
404 Not Found
```

## 🌐 CORS

O projeto utiliza o pacote `@fastify/cors` para configurar o Cross-Origin Resource Sharing:

```typescript
server.register(cors, {
  origin: "*"
});
```

Essa configuração permite que a API receba requisições de diferentes origens, facilitando sua utilização por aplicações frontend durante o desenvolvimento.

> **Nota:** `origin: "*"` é adequado para fins de estudo e desenvolvimento. Em uma aplicação de produção, é recomendado restringir as origens permitidas.

## ▶️ Como executar o projeto

### 1. Clone o repositório

```bash
git clone https://github.com/seu-usuario/f1-api.git
```

### 2. Entre na pasta

```bash
cd f1-api
```

### 3. Instale as dependências

```bash
npm install
```

### 4. Execute o projeto

```bash
npm run dev
```

A API estará disponível em:

```text
http://localhost:3333
```

## 🧪 Testando a API

Você pode testar os endpoints utilizando ferramentas como:

* Insomnia
* Postman
* Thunder Client
* Navegador, para endpoints GET
* JavaScript/TypeScript utilizando `fetch`

Exemplo:

```javascript
fetch("http://localhost:3333/drivers")
  .then(response => response.json())
  .then(data => console.log(data));
```

## 📚 O que pratiquei neste projeto

Este projeto foi desenvolvido para colocar em prática conceitos fundamentais de desenvolvimento backend:

* Criação de uma API REST
* Desenvolvimento com **Node.js**
* Utilização do **Fastify**
* Tipagem com **TypeScript**
* Criação de rotas HTTP
* Parâmetros dinâmicos (`/drivers/:id`)
* Busca de dados utilizando `find()`
* Tratamento de respostas `404`
* Status codes HTTP
* Configuração de CORS
* Estruturação de dados em arrays de objetos
* Consumo de uma API através de `fetch`

## 🔮 Próximos passos

Algumas melhorias que podem ser implementadas futuramente:

* [ ] Adicionar cadastro de equipes
* [ ] Adicionar cadastro de pilotos
* [ ] Implementar atualização e exclusão de registros
* [ ] Adicionar validação dos dados
* [ ] Utilizar banco de dados
* [ ] Criar testes automatizados
* [ ] Documentar a API com Swagger/OpenAPI
* [ ] Criar uma aplicação frontend para consumir a API

## 👩‍💻 Autora

**Carolina Lira**

Estudante de **Sistemas de Informação**, com interesse em desenvolvimento de software, APIs, tecnologia e desenvolvimento web.

🔗 [GitHub](https://github.com/carolinatlira)

---

⭐ Projeto desenvolvido para fins de estudo e portfólio.
