## FinApi - Financeira

### Requisitos e Regras de Negócio

#### Users

    [x] Should be able to create a new user

        [x] Para que esse teste passe, você deve permitir que um usuário seja criado e retorne um JSON com o usuário criado.
        [x] Também é necessário que você retorne a resposta com o código `201`.

    [x] Should not be able to create a new user when username already exists

        [x] Para que esse teste passe, antes de criar um usuário você deve validar se outro usuário com o mesmo username já existe.
        [x] Caso exista, retorne uma resposta com status 400 e um json de erro.
        [x] A mensagem pode ser de sua escolha, desde que a propriedade seja error.
        
#### Midlleware

    [x] Codificar o Middleware

        [x] Deve pegar o username do usuário no header da requisição, verificar se esse usuário existe e então colocar esse usuário dentro da request antes de chamar a função next.
        [x] Caso o usuário não seja encontrado, você deve retornar uma resposta contendo status 404 e um json no seguinte formato de erro.

#### Todos

    [x] Should be able to list all user's todos

        [x] Para que esse teste passe, na rota GET /todos é necessário pegar o usuário que foi repassado para o request no middleware checkExistsUserAccount.
        [x] Retornar a lista todos que está no objeto do usuário conforme foi criado para satisfazer o primeiro teste.
    
    [x] Should be able to create a new todo

        [x] Para que esse teste passe, na rota POST /todos é necessário pegar o usuário que foi repassado para o request no middleware checkExistsUserAccount.
        [x] Pegar também o title e o deadline do corpo da requisição e adicionar um novo todo na lista todos que está no objeto do usuário.
        [x] Utilizar a estrutura padrão de um todo e o objeto do todo deve ser retornado na resposta da requisição com status 201.

    [x] Should be able to update a todo

        [x] Para que esse teste passe, na rota PUT /todos/:id é necessário atualizar um todo existente, recebendo o title e o deadline pelo corpo da requisição e o id presente nos parâmetros da rota.

    [x] Should not be able to update a non existing todo

        [x] Para que esse teste passe, você não deve permitir a atualização de um todo que não existe e retornar uma resposta contendo um status 404 e um json no seguinte formato de erro.

    [x] Should be able to mark a todo as done

        [x] Para que esse teste passe, na rota PATCH /todos/:id/done você deve mudar a propriedade donede um todo de false para true, recebendo o id presente nos parâmetros da rota.

    [x] Should not be able to mark a non existing todo as done

        [x] Para que esse teste passe, você não deve permitir a mudança da propriedade done de um todo que não existe e retornar uma resposta contendo um status 404 e um json no seguinte formato de erro.

    [x] Should be able to delete a todo

        [x] Para que esse teste passe, DELETE /todos/:id você deve permitir que um todo seja excluído usando o id passado na rota. 
        [x] O retorno deve ser apenas um status 204 que representa uma resposta sem conteúdo.

    [x] Should not be able to delete a non existing todo

        [x] Para que esse teste passe, você não deve permitir excluir um todo que não exista e retornar uma resposta contendo um status 404 e um json no seguinte formato de erro.