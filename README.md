
# CRUD Fullstack

Uma aplicação completa, com ReactJS no frontend, NodeJS no backend (API) e o MySQL no banco de dados.


## Documentação da API

#### Retorna todos os itens

```js
    const q = "SELECT * FROM usuarios";

        db.query(q, (err, data) => {
            if (err) return res.json(err);

        return res.status(200).json(data);
    });
```

| Parâmetro   | Tipo       | Descrição                           |
| :---------- | :--------- | :---------------------------------- |
| `api_key` | `string` | **Obrigatório**. A chave da sua API |

#### Insere um item

```js
  const q = "INSERT INTO usuarios(`nome`, `email`, `fone`, `data_nascimento`) VALUES(?)";

  const values = [
    req.body.nome,
    req.body.email,
    req.body.fone,
    req.body.data_nascimento,
  ];

  db.query(q, [values], (err) => {
    if (err) return res.json(err);

    return res.status(200).json("Usuário criado com sucesso.");
  });
```

| Parâmetro   | Tipo       | Descrição                                   |
| :---------- | :--------- | :------------------------------------------ |
| `id`      | `string` | **Obrigatório**. O ID do item que você quer |

#### Atualiza um item

```js
  const q = "UPDATE usuarios SET `nome` = ?, `email` = ?, `fone` = ?, `data_nascimento` = ? WHERE `id` = ?";

  const values = [
    req.body.nome,
    req.body.email,
    req.body.fone,
    req.body.data_nascimento,
  ];

  db.query(q, [...values, req.params.id], (err) => {
    if (err) return res.json(err);

    return res.status(200).json("Usuário atualizado com sucesso.");
  });
```

#### Deleta um item

```js
  const q = "DELETE FROM usuarios WHERE `id` = ?";

  db.query(q, [req.params.id], (err) => {
    if (err) return res.json(err);

    return res.status(200).json("Usuário deletado com sucesso.");
  });
```
## Instalação

Entre em cada pasta e aplique o comando "yarn".

```bash
  cd api
  yarn
  cd ..
  cd frontend
  yarn
```
    
Ou "npm install".

```bash
  cd api
  npm install
  cd ..
  cd frontend
  npm install
```
    
## Autores

- [@CauanDZN](https://www.github.com/CauanDZN)

