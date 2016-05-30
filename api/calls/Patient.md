**Patient**
----
> Resource that inserts, updates and get patient information

###Get

| resource                 | method         | parameters                              |
|:-------------------------|:---------------| ----------------------------------------|
| **/api/patients/:id**    | **GET**        | **id**: string                          |
   
*  **Headers**

   **Required:**
   `x-access-token=[valid token received at login]`

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ patient object }`
 
* **Error Response:**

  * **Code:** 404 Not Found <br />
    **Content:** `{ error : "Paciente não existente." }`

###Update

| resource                 | method         | parameters                              |
|:-------------------------|:---------------| ----------------------------------------|
| **/api/patients/:id**    | **PUT**        | **name**: string, **email**: string, **streetName**: string, **zipCode**: string, **city**: string, **state**: string, **country**: string|
  
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
      **Content:** `{ error : "E-mail já existente." }`

###Update Image

| resource                 | method         | parameters                              |
|:-------------------------|:---------------| ----------------------------------------|
| **/api/patients/:id/image**    | **PUT**        | **profileImage**: image, |
  
*  **URL Params**

   **Required:**
   `profileImage=[file]`
   
*  **Body**

   **Required:**
   `form-data`
   
*  **Headers**

   **Required:**
   `x-access-token=[valid token received at login]`
   
* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ sucess: "ok" }`
