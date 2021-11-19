## FinApi - Financeia

### Requisitos e Regras de Negócio

    [x] Should be able to create a new user

        [x] Para que esse teste passe, você deve permitir que um usuário seja criado e retorne um JSON com o usuário criado.
        [x] Também é necessário que você retorne a resposta com o código `201`.

    [x] Should not be able to create a new user when username already exists

        [x] Para que esse teste passe, antes de criar um usuário você deve validar se outro usuário com o mesmo username já existe.
        [x] Caso exista, retorne uma resposta com status 400 e um json de erro.
        [x] A mensagem pode ser de sua escolha, desde que a propriedade seja error.
        

