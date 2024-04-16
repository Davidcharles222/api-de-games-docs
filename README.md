# API de Games
Esta API é utilizada para TAL e TAL...
## Endpoints
### GET /games
Esse endpoint é responsável por retornar a listagem de todos os games cadastrados no banco de dados.
#### Parametros
Nenhum
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber a listagem de todos os games.

Exemplo de resposta:
```
[
    {
        "id": 65,
        "title": "Sea of thieves",
        "year": "2018",
        "price": "40"
    },
    {
        "id": 2,
        "title": "Minecraft",
        "year": 2012,
        "price": 20
    },
    {
        "id": 2323,
        "title": "God of War",
        "price": "20",
        "year": "2000"
    }
]
```
##### Fala na autenticação! 401
Caso essa resposta acontaça, isso significa que acontenceu alguma falha durante o processo de autenticação da requisição. Motivos: Token
inválido, Token expirado.

Exemplo de resposta:
```
{
    "err": "Token inválido"
}
```

### POST /auth
Esse endpoint é responsável por fazer o processo de login.
#### Parametros
email: E-mail do usuário cadastrado no sistema.

password: Senha do usuário cadastrado no sistema, com aquele determinado e-mail.

Exemplo:

```
{
    "email":"victordevtb@guiadoprogramador.com",
    "password":"node123"
}
```

#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber o token JWT para cconseguir acessar endpoints protegidos na API.

Exemplo de resposta:
```
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJ2aWN0b3JkZXZ0YkBndWlhZG9wcm9ncmFtYWRvci5jb20iLCJpYXQiOjE3MTMyMzExNDgsImV4cCI6MTcxMzQwMzk0OH0.VyMZjTYuSh9y0Jkwh88KIW9r-q_7UG5nq2eWZeTSpdM"
}
```

##### Fala na autenticação! 401
Caso essa resposta acontaça, isso significa que acontenceu alguma falha durante o processo de autenticação da requisição. Motivos: Senha
ou e-mail incorretos.

Exemplo de resposta:
```
{err: "Credenciais inválidas!"}
```
