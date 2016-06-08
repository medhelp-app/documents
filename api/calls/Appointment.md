**Appointment**
----

###Insert
####1. Inserts new appointment

| resource            | method         | parameters                              |
|:--------------------|:---------------| ----------------------------------------|
| **/api/doctors/:id/appointments**    | **POST**       | **patientId**: string, **availabilityId**: string, **date**: string|
*  **URL Params**

   **Required:**
   `id=[string]`
   
*  **Headers**

   **Required:**
   `x-access-token=[valid token received at login]`

**Sample Call**
  ```javascript
  $http.post('/api/doctors/1/appointments', {
  		"patientId": 2,
  		"availabilityId": 1,
  		"date": 2016-02-16,
    }).then(success, error);
  ```

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ "success": "true" }`
 
* **Error Response:**

  * **Code:** 404 Bad Request <br />
      **Content:** `{ "error" : "Doutor não existene." }`
      
###GET
####1. get all doctor's appointment

| resource            | method         | parameters                              |
|:--------------------|:---------------| ----------------------------------------|
| **/api/doctors/:id/appointments**    | **GET**       | |
*  **URL Params**

   **Required:**
   `id=[string]`
   
*  **Headers**

   **Required:**
   `x-access-token=[valid token received at login]`

**Sample Call**
  ```javascript
  $http.get('/api/doctors/1/appointments', [{
  		"patientId": 2,
  		"availabilityId": 1,
  		"date": 2016-02-16,
    }, {
      
    }]).then(success, error);
  ```

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ "success": "true" }`
 
* **Error Response:**

  * **Code:** 404 Bad Request <br />
      **Content:** `{ "error" : "Paciente não existene." }`
