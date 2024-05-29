<h1 align="center">
Streams Node.js
<br>
<br>
</h1>

<div align="right">
    Clique <a href="https://github.com/luc-ribeiro/streams-node/blob/main/README-PTBR.md">aqui</a> para ver a versão em Português.
</div>
<br>

## 💻 Project
This project was created during the Node.js course by Rocketseat.

The project consists of creating a simple API using only Node.js without frameworks.
The goal is to practice the fundamentals of this technology and address the concept of <strong>streams</strong>.

Streams are a way to read and process files while they are being sent to the server.
Every input and output port in Node.js is a stream. It's possible to process large files while they are being sent to the server.

## 🚀 Technologies

- **Node.js** 
- **JavaScript**

## Endpoints

#### Listing Users

<details>
 <summary><code>GET</code> <code><b>/users</b>?search={username or user email}</code> <code>(returns all users or filtered users)</code></summary>

##### Parameters

> | name   |  type    | data type | description                       |
> |--------|----------|-----------|-----------------------------------|
> | search | optional | string    | User email or name to filter      |

##### Responses

> | http code | content-type       | response                                           |
> |-----------|--------------------|----------------------------------------------------|
> | `200`     | `application/json` | JSON containing all users or only filtered users   |

##### cURL Example

> ```javascript
>  curl -X GET -H "Content-Type: application/json" http://localhost:3333/users
> ```

</details>

#### Creating a New User

<details>
 <summary><code>POST</code> <code><b>/users</b></code> <code>(creates a new user)</code></summary>

##### Parameters

> | name  |  type    | data type | description             |
> |-------|----------|-----------|-------------------------|
> | email | required | string    | User email              |
> | name  | required | string    | User name               |

##### Responses

> | http code | content-type                 | response                         |
> |-----------|------------------------------|----------------------------------|
> | `201`     | `text/plain;charset=UTF-8`   | `User created successfully`      |
> | `400`     | `application/json`           | `{"code":"400","message":"Bad Request"}` |
> | `405`     | `text/html;charset=utf-8`    | None                             |

##### cURL Example

> ```javascript
>  curl -X POST -H "Content-Type: application/json" --data @post.json http://localhost:3333/users
> ```

</details>

#### Editing a User

<details>
 <summary><code>PUT</code> <code><b>/users/{id}</b></code> <code>(edits a user)</code></summary>

##### Parameters

> | name |  type    | data type | description                       |
> |------|----------|-----------|-----------------------------------|
> | id   | required | int       | User unique identifier            |

##### Body

> | name  |  type    | data type | description                       |
> |-------|----------|-----------|-----------------------------------|
> | email | required | string    | Email of the user to be edited    |
> | name  | required | string    | Name of the user to be edited     |

##### Responses

> | http code | content-type                 | response                         |
> |-----------|------------------------------|----------------------------------|
> | `204`     | `text/plain;charset=UTF-8`   | User changed successfully        |
> | `400`     | `application/json`           | `{"code":"400","message":"Bad Request"}` |
> | `405`     | `text/html;charset=utf-8`    | None                             |

##### cURL Example

> ```javascript
>  curl -X PUT -H "Content-Type: application/json" --data @put.json http://localhost:3333/users/id
> ```

</details>

#### Deleting a User

<details>
 <summary><code>DELETE</code> <code><b>/users/{id}</b></code> <code>(deletes a user)</code></summary>

##### Parameters

> | name |  type    | data type | description                       |
> |------|----------|-----------|-----------------------------------|
> | id   | required | int       | User unique identifier            |

##### Responses

> | http code | content-type                 | response                         |
> |-----------|------------------------------|----------------------------------|
> | `204`     | `text/plain;charset=UTF-8`   | User deleted successfully        |
> | `400`     | `application/json`           | `{"code":"400","message":"Bad Request"}` |
> | `405`     | `text/html;charset=utf-8`    | None                             |

##### cURL Example

> ```javascript
>  curl -X DELETE -H "Content-Type: application/json" http://localhost:3333/users/id
> ```

</details>

<br>

## :page_facing_up: How to Use

- Clone this repository:

```sh
  $ git clone https://github.com/luc-ribeiro/streams-nodejs.git
```

- Run the command:

```sh
  # with npm
  $ npm run dev

  # with yarn
  $ yarn dev
```

- The project will run at `localhost:3333`

## Testing Streams

- Run the command in the project root:

```sh
  $ node streams/stream-http-server.js
```

```sh
  $ node streams/fake-upload-to-http-stream.js
```

View the gradual sending of a count from 1 to 5 in the `stream-http-server.js` terminal.
