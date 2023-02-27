# PiggyBank

Uma API para o sistema de controle de gastos pessoais

## Endpoints
- Despesas
    -Cadastrar
    -Listar todas
    -Apagar
    -Alterar 
    -Mostrar os detalhes
- Contas
    -Cadastrar
    -Listar todas
    -Apagar
    -Alterar 
    -Mostrar os detalhes
- Categorias

---
### Cadastrar Despesas
`POST` /piggybank/api/despesa

| campo | tipo | obrigatório | descrição 
|-------|------|-------------|-----------
| valor | decimal| sim | é o valor da despesa. deve ser maior que zero
| categoria_id | int | sim | é o id de uma categoria
| conta_id | int | sim | é o id da conta previamente
| data | data | sim | é da despesa 
| descricao | texto | nao | uma descricao da despesa com máximo de 255 caracteres 

**Exemplo de corpo do request**

```js

{
    "valor" : 100.00,
    "categoria_id" : 1,
    "conta_ id" : 1,
    "data" : "2023-01-21",
    "descricao" : "cinema com os amigos"
}

```

**Códigos de Repsosta**

| codigo | descricao
|--------|-----------
| 201 | despesa cadastrada com sucesso
| 400 | erro na validaçao dos dadios da requisição

---

### Detalhar Despesa 
`GET` /piggybank/api/despesa/{id}

**Exemplo do corpo para resposta**

```js

{
    "valor" : 100.00,
   "categoria" : {
        "categoria_id" : 1,
        "nome" : "lazer"
   },
    "conta" : {
        "conta_ id" : 1,
        "nome" : "itaú"
    },
    "data" : "2023-01-21",
    "descricao" : "cinema com os amigos"
}

```
