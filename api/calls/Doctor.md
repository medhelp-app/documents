**Doctor**
----
  Resources that inserts, update and delete doctor information

###Get

| resource            | method         | parameters                              |
|:--------------------|:---------------| ----------------------------------------|
| **/api/doctors/:id**      | **GET**       | **id**: string|

*  **URL Params**

   **Required:**
   `id=[string]`
   
*  **Headers**

   **Required:**
   `x-access-token=[valid token received at login]`

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ doctor object }`

  * **Code:** 404 Bad Request <br />
      **Content:** `{ error : "Médico não existene." }`

###Update

| resource            | method         | parameters                              |
|:--------------------|:---------------| ----------------------------------------|
| **/api/doctors/:id**      | **PUT**       | **profileImage**: image, **name**: string, **email**: string, **streetName**: string, **zipCode**: string, **city**: string, **state**: string, **country**: string, **crm**:int|

*  **URL Params**

   **Required:**
   `name=[string]`
   `email=[string]`
   
*  **Headers**

   **Required:**
   `x-access-token=[valid token received at login]`

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ sucess: "ok" }`
 
* **Error Response:**

  * **Code:** 400 Bad Request <br />
    **Content:** `{ error : "E-mail inválido." }`

  * **Code:** 400 Bad Request <br />
      **Content:** `{ error : "E-mail duplicado." }`

  * **Code:** 400 Bad Request <br />
      **Content:** `{ error : "O campo 'nome' e 'e-mail' são obrigatórios." }`

  * **Code:** 404 Bad Request <br />
      **Content:** `{ error : "Médico não existene." }`
