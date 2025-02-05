# Workshop MongoDB com Spring Boot

Este projeto é uma API REST desenvolvida com **Spring Boot** e **MongoDB**, criada para gerenciar posts de um sistema de blog. Ele permite buscar posts por **ID**, **título** e **intervalo de datas**.

## Tecnologias Utilizadas

- **Java 21**
- **Spring Boot 3+**
- **Spring Data MongoDB**
- **Maven**
- **MongoDB**

## Estrutura do Projeto

O projeto segue a arquitetura em camadas:

- **Controller (`PostResource`)**: Define os endpoints da API.
- **Service (`PostService`)**: Contém a lógica de negócios e chamadas ao repositório.
- **Repository (`PostRepository`)**: Interface para acesso ao banco de dados MongoDB.
- **Model (`Post`)**: Representa a entidade Post.
- **Utilitários (`URL`)**: Contém métodos auxiliares para manipulação de URLs e datas.

## Endpoints da API

### 1. Buscar post por ID

```http
GET /posts/{id}
```
- Retorna um post específico com base no seu **ID**.
- Exemplo de resposta:
  ```json
  {
    "id": "65e3b9f12a3c5f0012a45678",
    "title": "Meu primeiro post",
    "body": "Conteúdo do post",
    "date": "2025-02-05T12:00:00Z"
  }
  ```

### 2. Buscar posts por título

```http
GET /posts/titlesearch?text=exemplo
```
- Retorna uma lista de posts cujo **título** contenha o texto especificado.

### 3. Busca completa (Full Search)

```http
GET /posts/fullsearch?text=exemplo&minDate=2024-01-01&maxDate=2025-01-01
```
- Retorna posts filtrando por **conteúdo**, **data mínima** e **data máxima**.
- Se os parâmetros de data não forem informados, assume **1970-01-01** como data mínima e a **data atual** como máxima.

## Como Executar o Projeto

1. Clone o repositório:
   ```sh
   git clone https://github.com/Brenner-Resende/workshop-springboot-mongodb.git
   cd workshop-mongo
   ```

2. Instale as dependências com Maven:
   ```sh
   mvn clean install
   ```

3. Configure o MongoDB localmente ou utilize um banco na nuvem.

4. Execute a aplicação:
   ```sh
   mvn spring-boot:run
   ```

5. Acesse a API em `http://localhost:8080/posts`

## Autor

Projeto desenvolvido por **Brenner Resende** no contexto de estudos sobre **Spring Boot e MongoDB**.

---

Este repositório pode ser atualizado com novas funcionalidades e melhorias. Contribuições são bem-vindas! 🚀