**Prescription**
----
Patient prescription information resource

###Get
####1. Returns list of prescriptions

| resource            | method         | parameters                              |
|:--------------------|:---------------| ----------------------------------------|
| **/api/patients/:id/prescriptions**     | **GET**       | **id**: string|

*  **URL Params**

   **Required:**
   `id=[string]`
   
*  **Headers**

   **Required:**
   `x-access-token=[valid token received at login]`

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    
    ```javascript
    {
    	"prescriptions": [{
    		"id": "1",
    		"patientId": "2",
    		"doctorId": "3",
    		"problem": "Dor de cabeça",
    		"medicines": [{
    			"id": "1",
    			"name": "Apirina",
    			"amount": "2",
    			"occurence:" : "3 vezes ao dia",
    			"description": "Paciente apresenta dor de cabeça",
    			"note": "Uma observação qualquer que o médico queria adicionar"
    			
    		}, {
    			"id": "2",
    			"problem": "Rivotril",
    			"amount": "1",
    			"occurence:" : "Antes de dormir",
    			"description": "Paciente apresenta sintomas que devem ser tratados com esta medicação",
    			"note": "Esta medicação não deve ser tomada mais de uma vez ao dia"
    		}]
    	}, {
    		"id": "2",
    		"problem": "Infecção",
    		"medicines": [{
    			"...": "..."
    		}]
    	}, {
    		"...": "..."
    	}]
    }
    ```

  * **Code:** 404 Bad Request <br />
      **Content:** `{ "error" : "Paciente não existene." }`
      
####2. Returns specific prescription

| resource            | method         | parameters                              |
|:--------------------|:---------------| ----------------------------------------|
| **/api/patients/:id/prescriptions/:id**      | **GET**       | **id**: string|

*  **URL Params**

   **Required:**
   `id=[string]`
   
*  **Headers**

   **Required:**
   `x-access-token=[valid token received at login]`

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    ```javascript
    {
    	{
    		"id": "1",
    		"patientId": "2",
    		"doctorId": "3",
    		"problem": "Dor de cabeça",
    		"medicines": [{
    			"id": "1",
    			"name": "Apirina",
    			"amount": "2",
    			"occurence:" : "3 vezes ao dia",
    			"description": "Paciente apresenta dor de cabeça",
    			"note": "Uma observação qualquer que o médico queria adicionar"
    			
    		}, {
    			"id": "2",
    			"problem": "Rivotril",
    			"amount": "1",
    			"occurence:" : "Antes de dormir",
    			"description": "Paciente apresenta sintomas que devem ser tratados com esta medicação",
    			"note": "Esta medicação não deve ser tomada mais de uma vez ao dia"
    		}
    }
    ```

  * **Code:** 404 Bad Request <br />
      **Content:** `{ error : "Paciente não existene." }`
  * **Code:** 404 Bad Request <br />
      **Content:** `{ error : "Prescrição não existente." }`

###Insert
####1. Inserts new prescription

| resource            | method         | parameters                              |
|:--------------------|:---------------| ----------------------------------------|
| **/api/patients/:id/prescriptions**     | **POST**       | **doctorId**: string, **problem**: string, **medicines**: list|
*  **URL Params**

   **Required:**
   `id=[string]`
   
*  **Headers**

   **Required:**
   `x-access-token=[valid token received at login]`

**Sample Call**
  ```javascript
  $http.post('/api/patients/1/prescriptions', {
  		"doctorId": "3",
  		"problem": "Dor de cabeça",
  		"medicines": [{
  			"id": "1",
  			"name": "Apirina",
  			"amount": "2",
  			"occurence:" : "3 vezes ao dia",
  			"description": "Paciente apresenta dor de cabeça",
  			"note": "Uma observação qualquer que o médico queria adicionar"
  			
  		}, {
  			"id": "2",
  			"problem": "Rivotril",
  			"amount": "1",
  			"occurence:" : "Antes de dormir",
  			"description": "Paciente apresenta sintomas que devem ser tratados com esta medicação",
  			"note": "Esta medicação não deve ser tomada mais de uma vez ao dia"
  		}]
    }).then(success, error);
  ```

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ "success": "true" }`
 
* **Error Response:**

  * **Code:** 404 Bad Request <br />
      **Content:** `{ "error" : "Paciente não existene." }`
    
###Update
####1. Updates a prescription
| resource            | method         | parameters                              |
|:--------------------|:---------------| ----------------------------------------|
| **/api/patients/:id/prescriptions/:id**       | **PUT**       | **doctorId**: string, **problem**: string, **medicines**: list|bo

*  **URL Params**

   **Required:**
   `id=[string]`
   
*  **Headers**

   **Required:**
   `x-access-token=[valid token received at login]`

**Sample Call**
  ```javascript
  $http.post('/api/patients/1/prescriptions', {
  		"doctorId": "3",
  		"problem": "Dor de cabeça",
  		"medicines": [{
  			"id": "1",
  			"name": "Apirina",
  			"amount": "2",
  			"occurence:" : "3 vezes ao dia",
  			"description": "Paciente apresenta dor de cabeça",
  			"note": "Uma observação qualquer que o médico queria adicionar"
  			
  		}]
    }).then(success, error);
  ```

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ "success": "true" }`
 
* **Error Response:**

  * **Code:** 404 Bad Request <br />
      **Content:** `{ "error" : "Paciente não existene." }`
