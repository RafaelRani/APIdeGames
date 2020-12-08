# API de Games
Esta API é ultilizada para tal e tal
## Endpoints
### GET /games
Esse endpoint é responsável por retornar a listagem de todos os games cadastrados no banco de dados
#### Parâmetros
Nenhum
#### Respostas
##### OK 200
Caso essa resposta aconteça, você vai receber a listagem de todos os games.
Exemplo de resposta:
```
[
    {
        "id": 23,
        "title": "Call of Duty",
        "year": 2019,
        "price": 68
    },
    {
        "id": 65,
        "title": "Sea of Thieves",
        "year": 2018,
        "price": 48
    },
    {
        "id": 2,
        "title": "Minecraft",
        "year": 2012,
        "price": 28
    }
]
```
##### Falha na autenticação: 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: token inválido,
token expirado.
Exemplo de resposta:
```
{
    "err": "token inválido!"
}
```

### POST /auth
Esse endpoint é responsável por fazer o processo de login.
#### Parâmetros
Email: email do usuário cadastrado no sistema

Password: senha do usuário cadastrado no sistema, com aquele determinado email

Exemplo:
```
{
    "email": "ranny008@hotmail.com",
    "password": "1234"
}
```
#### Respostas
##### OK 200
Caso essa resposta aconteça, você vai receber o token JWT para conseguir acessar endpoints protegidos na API.
Exemplo de resposta:
```
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJyYW5ueTAwOEBob3RtYWlsLmNvbSIsImlhdCI6MTYwNzQzNDU5OSwiZXhwIjoxNjA3NjA3Mzk5fQ.LfWMibX0vF3MgkJ9elc187t1-6yF3GDQvTKR_KUaSUU"
}
```
##### Falha na autenticação: 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: senha ou email incorretos.
Exemplo de resposta:
```
{
    "err": "credenciais inválidas!"
}
```
