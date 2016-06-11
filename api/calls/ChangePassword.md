**Change Password**
----
Update password and forgotten Password

###PUT
####1. Update password

| resource            | method         | parameters                              |
|:--------------------|:---------------| ----------------------------------------|
| **/api/users/:id/password/**      | **PUT**       | **id**: string, **oldPassword**: string, **newPassword**: string,**reNewPassword**: string|

*  **URL Params**

   **Required:**
   `id=[string]`
   
*  **Headers**

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
    ```javascript
    {
    	success : 'true'
    }
    ```

  * **Code:** 404 Bad Request <br />
      **Content:** `{ "error" : "Usuário não existe!" }`
  * **Code:** 404 Bad Request <br />
      **Content:** `{ "error" : "Senha antiga incorreta!." }`
  * **Code:** 404 Bad Request <br />
      **Content:** `{ "error" : "Nova senha inválida!" }`
  * **Code:** 404 Bad Request <br />
      **Content:** `{ "error" : "Não foi possível alterar a senha!" }`
      
####2. Recovery forgotten password

| resource            | method         | parameters                              |
|:--------------------|:---------------| ----------------------------------------|
| **/api/users/:id/password/forgottenPassword**      | **PUT**       | **tokenGenerated:**: string,**newPassword:**: string,**reNewPassword:**: string |

*  **URL Params**

   **Required:**
   `id=[string]`
   
* **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    ```javascript
    {
    	success : 'true'
    }
    ```

  * **Code:** 404 Bad Request <br />
      **Content:** `{ error : "Usuário não existe." }`
  * **Code:** 404 Bad Request <br />
      **Content:** `{ error : "Error ao buscar usuário!" }`
  * **Code:** 404 Bad Request <br />
      **Content:** `{ error : "Usuário não existe!" }`

###GET
####1. Send email for recovery forgotten password

| resource            | method         | parameters                              |
|:--------------------|:---------------| ----------------------------------------|
| **/api/users/:email/password/forgottenPassword**      | **GET**       |  |
*  **URL Params**

   **Required:**
   `email=[string]`
   
*  **Headers**
   
`

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ "success": "true" }`
* **Email send:**
  **url** `http://medhelp-app.github.io/senha?id=1&tokenGenerated=abc123`
* **Error Response:**

  * **Code:** 404 Bad Request <br />
      **Content:** `{ "error" : "Usuário não existe!" }`
   * **Code:** 404 Bad Request <br />
      **Content:** `{ "error" : "Error ao buscar usuário!" }`
  * **Code:** 404 Bad Request <br />
      **Content:** `{ "error" : "Error ao enviar email!" }`
