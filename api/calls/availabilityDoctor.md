**Availability**
----

###Insert
####1. Inserts new Availability

| resource            | method         | parameters                              |
|:--------------------|:---------------| ----------------------------------------|
| **/api/doctors/:id/availability**    | **POST**       | **weekday**: string, **startHour**: string, **endHour**: string|
*  **URL Params**

   **Required:**
   `id=[string]`

*  **Headers**

   **Required:**
   `x-access-token=[valid token received at login]`

**Sample Call**
  ```javascript
  $http.post('/api/doctors/1/availability', {
  		"weekday": 'monday',
  		"startHour": '09:30',
  		"endHour": '12:00'
    }).then(success, error);
  ```

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ "success": "true" }`

* **Error Response:**

  * **Code:** 404 Bad Request <br />
      **Content:** `{ "error" : "Doutor não existene." }`

###GET
####1. get all doctor's availability

| resource            | method         | parameters                              |
|:--------------------|:---------------| ----------------------------------------|
| **/api/doctors/:id/availability**    | **GET**       | |
*  **URL Params**

   **Required:**
   `id=[string]`

*  **Headers**

   **Required:**
   `x-access-token=[valid token received at login]`

**Sample Call**
  ```javascript
  $http.get('/api/doctors/1/appointments').then(success, error);
  ```

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ [{
                      		"_id": 1,
                      		"doctorId": 1,
                      		"weekday": monday,
                      		"startHour": '09:30',
                            "endHour": '12:00'

                        }, {
                            "_id": 2,
                            "doctorId": '1',
                            "weekday": 'friday',
                            "startHour": '14:00',
                            "endHour": '16:00'
                        }] }`

* **Error Response:**

  * **Code:** 404 Bad Request <br />
      **Content:** `{ "error" : "Paciente não existe." }`

####1. get doctor's availability

| resource            | method         | parameters                              |
|:--------------------|:---------------| ----------------------------------------|
| **/api/doctors/availability/:id**    | **GET**       | |
*  **URL Params**

   **Required:**
   `id=[string]`

*  **Headers**

   **Required:**
   `x-access-token=[valid token received at login]`

**Sample Call**
  ```javascript
  $http.get('/api/doctors/appointments/1').then(success, error);
  ```

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{
                   	"_id": 1,
                   	"doctorId": 1,
                   	"weekday": monday,
                   	"startHour": '09:30',
                    "endHour": '12:00'
                  }`

* **Error Response:**

  * **Code:** 404 Bad Request <br />
      **Content:** `{ "error" : "Disponibilidade não existe." }`

###Update

| resource            | method         | parameters                              |
|:--------------------|:---------------| ----------------------------------------|
| **/api/doctors/availability/:id**    | **PUT**       | **weekday**: string, **startHour**: string, **endHour**: string|
*  **URL Params**

   **Required:**
   `id=[string]`

*  **Headers**

   **Required:**
   `x-access-token=[valid token received at login]`

**Sample Call**
  ```javascript
  $http.put('/api/doctors/availability/:id', {
  		"weekday": 'sumday',
  		"startHour": '09:30',
  		"endHour": '12:00'
    }).then(success, error);
  ```

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ "success": "true" }`

###Delete

| resource            | method         | parameters                              |
|:--------------------|:---------------| ----------------------------------------|
| **/api/doctors/availability/:id**    | **DELETE**       | |
*  **URL Params**

   **Required:**
   `id=[string]`

*  **Headers**

   **Required:**
   `x-access-token=[valid token received at login]`

**Sample Call**
  ```javascript
  $http.delete('/api/doctors/availability/:id').then(success, error);
  ```

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ "success": "true" }`