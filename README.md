<h1 align="center">
Streams Node.js
<br>
<br>
</h1>
<br>

## 💻 Projeto
Este projeto foi criado durante o curso de Node.js da Rocketseat.

O projeto consiste na criação de uma API simples, utilizando apenas o Node.js sem frameworks.
O objetivo é praticar os fundamentos dessa tecnologia e abordar o conceito de <strong>streams</strong>.

Streams é uma forma de ler e processar arquivos, enquanto os mesmos estão sendo enviados para o servidor.
Toda porta de entrada e saída no Node, é uma stream. É possível processar arquivos grandes enquanto eles estão sendo enviados para o servidor.

## 🚀 Tecnologias

- **Node.js** 
- **JavaScript**

## Endpoints

#### Listando usuários

<details>
 <summary><code>GET</code> <code><b>/users</b>?search={username or user e-mail}</code> <code>(retorna todos os usuários ou usuários filtrados)</code></summary>

##### Parâmetros

> | name      |  type     | data type               | description                                                           |
> |-----------|-----------|-------------------------|-----------------------------------------------------------------------|
> | search    |  optional | string                  | E-mail ou nome do usuário para filtrar                                |

##### Respostas

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `200`         | `application/json`                | JSON contendo todos os usuários ou somente os usuários filtrados    |

##### Exemplo cURL

> ```javascript
>  curl -X GET -H "Content-Type: application/json" http://localhost:3333/users
> ```

</details>

#### Criando um novo usuário

<details>
 <summary><code>POST</code> <code><b>/users</b></code> <code>(cria um novo user)</code></summary>

##### Parâmetros

> | name      |  type     | data type               | description                                                           |
> |-----------|-----------|-------------------------|-----------------------------------------------------------------------|
> | email     |  required | string                  | E-mail do usuário                                                     |
> | name      |  required | string                  | Nome do usuário                                                       |

##### Respostas

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `201`         | `text/plain;charset=UTF-8`        | `User created successfully`                                         |
> | `400`         | `application/json`                | `{"code":"400","message":"Bad Request"}`                            |
> | `405`         | `text/html;charset=utf-8`         | None                                                                |

##### Exemplo cURL

> ```javascript
>  curl -X POST -H "Content-Type: application/json" --data @post.json http://localhost:3333/users
> ```

</details>

#### Editando um usuário

<details>
 <summary><code>PUT</code> <code><b>/users/{id}</b></code> <code>(edita um usuário)</code></summary>

##### Parâmetros

> | name      |  type     | data type               | description                                                           |
> |-----------|-----------|-------------------------|-----------------------------------------------------------------------|
> | id        |  required | int                     | Identificador único do usuário                                        |

##### Body

> | name      |  type     | data type               | description                                                           |
> |-----------|-----------|-------------------------|-----------------------------------------------------------------------|
> | email     |  required | string                  | E-mail do usuário a ser editado                                       |
> | name      |  required | string                  | Nome do usuário a ser editado                                         |

##### Respostas

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `204`         | `text/plain;charset=UTF-8`        | User changed successfully                                           |
> | `400`         | `application/json`                | `{"code":"400","message":"Bad Request"}`                            |
> | `405`         | `text/html;charset=utf-8`         | None                                                                |

##### Exemplo cURL

> ```javascript
>  curl -X PUT -H "Content-Type: application/json" --data @put.json http://localhost:3333/users/id
> ```

</details>

#### Deletando um usuário

<details>
 <summary><code>DELETE</code> <code><b>/users/{id}</b></code> <code>(deleta um usuário)</code></summary>

##### Parâmetros

> | name      |  type     | data type               | description                                                           |
> |-----------|-----------|-------------------------|-----------------------------------------------------------------------|
> | id        |  required | int                     | Identificador único do usuário                                        |

##### Respostas

> | http code     | content-type                      | response                                                            |
> |---------------|-----------------------------------|---------------------------------------------------------------------|
> | `204`         | `text/plain;charset=UTF-8`        | User deleted successfully                                           |
> | `400`         | `application/json`                | `{"code":"400","message":"Bad Request"}`                            |
> | `405`         | `text/html;charset=utf-8`         | None                                                                |

##### Exemplo cURL

> ```javascript
>  curl -X DELETE -H "Content-Type: application/json" http://localhost:3333/users/id
> ```

</details>

<br>

## :page_facing_up: Como utilizar

- Faça um clone deste repositório:

```sh
  $ git clone https://github.com/luc-ribeiro/streams-nodejs.git
```

- Instale as dependências:

```sh
  # com npm
  $ npm install

  # com yarn
  $ yarn install
```

- Execute o comando:

```sh
  # com npm
  $ npm run dev

  # com yarn
  $ yarn dev
```

- O projeto rodará em `localhost:3333`

## Testando Streams

- Execute o comando na raiz do projeto:

```sh
  $ node streams/stream-http-server.js
```

```sh
  $ node streams/fake-upload-to-http-stream.js
```

Visualize o envio gradual de uma contagem de 1 até 5, no terminal do ```stream-http-server.js```

## :memo: License

Copyright © 2024 Lucas Ribeiro
