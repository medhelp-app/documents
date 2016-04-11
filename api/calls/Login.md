**Login**
----
  Receives an email and a password as parameters, returns success and json data about the user if the user exists, otherwise returns failure.

| resource         | method         | parameters                              |
|:-----------------|:---------------| ----------------------------------------|
| **/login**       | **POST**       | **email**: string, **password**: string |

* **URL**

  `/login`

* **Method:**

  `POST`
  
*  **URL Params**

   **Required:**
 
   `email=[string]`
   `password=[string]`

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ id: 12, name: "João Silva", session: "2016-02-03-12:23"}`
 
* **Error Response:**

  * **Code:** 401 Unauthorized <br />
    **Content:** `{ error : "Email and password does not match" }`

* **Sample Call:**

  ```javascript
    $.ajax({
      type : "POST",
      url: "/login",
      data: {
        'email': 'valid@email.com',
        'password': 'A24fS$0ad'
      },
      success : function(response) {
        // ...
      }
    });
  ```

* **Sample Response:**

  ```javascript{
    status: "ok",
    message-version: "1.0.0",
    message: {
      id: 12,
      name: "João Silva", 
      session: "2016-02-03-12:23"
    }
  }```