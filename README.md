# Instruções de uso da API

## Visão Geral
Esta API foi desenvolvida utilizando o **Strapi v3** e **Node.js na versão 14** e fornece endpoints para gerenciar coleções como `foods`, `places` e `people`.
A API segue o padrão REST e suporta operações CRUD (Create, Read, Update, Delete).

## Base URL
```
http://localhost:1337
```

## Autenticação
A API utiliza autenticação via **JWT**. Para acessar alguns recursos protegidos, é necessário obter um token.

### Registrar um novo usuário (username e email **unicos**)

**Endpoint:**
```
POST /auth/local/register
```
**Body (JSON):**
```json
{
  "username": "exemplo",
  "email": "exemplo@email.com",
  "password": "senha123"
}

```
### Login
**Endpoint:**
```
POST /auth/local
```
**Body (JSON):**
```json
{
  "identifier": "exemplo@email.com",
  "password": "senha123"
}
```
**Resposta:**
```json
{
  "jwt": "<TOKEN>",
  "user": {
    "id": 1,
    "username": "exemplo",
    "email": "exemplo@email.com"
  }
}
```

## Endpoints das Coleções (**Requer Autenticação**)

### **Foods**
#### Obter lista de alimentos 
```
GET /foods
```
**Resposta:**
```json
[
  {
    "id": 1,
    "name": "Steak",
    "image": {
      "url": "/uploads/steak.jpg"
    }
  }, {...},{...},
]
```

---

### **Places**
#### Obter lista de lugares
```
GET /places
```
**Resposta:**
```json
[
  {
    "id": 1,
    "name": "New York",
    "image": {
      "url": "/uploads/new-york.jpg"
    }
  }, {...},{...},
]
```

---

### **People**
#### Obter lista de pessoas
```
GET /people
```
**Resposta:**
```json
[
  {
    "id": 1,
    "name": "Obama",
    "image": {
      "url": "/uploads/obama.jpg"
    }
  }, {...},{...},
]
```

## Considerações finais
- Para acessar endpoints protegidos, adicione o token no cabeçalho da requisição:
  ```
  Authorization: Bearer <TOKEN>
  ```
- Recomendado utilizar um cliente HTTP para testar os endpoints.
- Consulte a documentação do Strapi para mais detalhes: [Strapi Docs](https://docs.strapi.io)

🚀 **API pronta para uso!**

