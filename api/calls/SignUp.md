**SignUp**
----
  Receives information about the user, inserts it in the database and if succeeds returns the user, returns failure otherwise.

| resource            | method         | parameters                              |
|:--------------------|:---------------| ----------------------------------------|
| **/api/users**      | **POST**       | **name**: string, **email**: string, **password**: string, **rePassword**: string|

* **URL**

  /signup

* **Method:**

  `POST`
  
*  **URL Params**

   **Required:**
   `name=[string]`
   `email=[string]`
   `password=[string]`
   `rePassword=[string]`

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ id: 15, name: "Maria Perreira", session: "2016-06-05-18:04"'}`
 
* **Error Response:**

  * **Code:** 400 Bad Request <br />
    **Content:** `{ error : "E-mail inválido." }`

  * **Code:** 400 Bad Request <br />
      **Content:** `{ error : "E-mail duplicado." }`

  * **Code:** 400 Bad Request <br />
      **Content:** `{ error : "Senhas inválidas." }`

  * **Code:** 400 Bad Request <br />
      **Content:** `{ error : "O campo 'name' é obrigatório." }`

* **Sample Call:**

  ```javascript
    $.ajax({
      type : "POST",
      url: "/api/users",
      data: {
      	'name': 'Maria Perreira'
        'email': 'valid@email.com',
        'password': 'K$0f3Md39s'
        'rePassword': 'K$0f3Md39s'
      },
      success : function(response) {
        // ...
      }
    });
  ```
  
  **angular**
  ```javascript
  $http.post('/api/users', {
      	'name': 'Maria Perreira'
        'email': 'valid@email.com',
        'password': 'K$0f3Md39s'
        'rePassword': 'K$0f3Md39s'
      }).then(success, error);
  ```

* **Sample Response:**

  ```javascript{
    status: "ok",
    message-version: "1.0.0",
    message: {
      id: 15,
      name: "Maria Perreira", 
      session: "2016-02-03-12:23"
    }
  }```
