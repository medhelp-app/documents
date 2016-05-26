**BodyParts**
----
Patient body parts information resource

```javascript
parts { rightArm, leftArm, rightLeg, leftLeg, stomach, chest, head }
```

###Get
####1. Returns list of body parts

| resource            | method         | parameters                              |
|:--------------------|:---------------| ----------------------------------------|
| **/api/patients/:id/bodyparts**      | **GET**       | **id**: string|

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
    	"bodyParts": [{
    		"id": "1",
    		"part": "leftArm",
    		"problems": [{
    			"id": "1",
    			"problem": "Braço quebrado",
    			"description": "Quebrei meu braço enquanto estava praticando esportes",
    			"occurredDate": "05/05/2012"
    		}, {
    			"id": "2",
    			"problem": "Punho torcido",
    			"description": "Punho torcido enquanto lutava",
    			"occurredDate": "01/02/2014"
    		}]
    	}, {
    		"id": "2",
    		"part": "rightArm",
    		"problems": [{
    			"...": "..."
    		}]
    	}, {
    		"...": "..."
    	}]
    }
    ```

  * **Code:** 404 Bad Request <br />
      **Content:** `{ "error" : "Paciente não existene." }`
      
####2. Returns specific body part

| resource            | method         | parameters                              |
|:--------------------|:---------------| ----------------------------------------|
| **/api/patients/:id/bodyparts/:part**      | **GET**       | **part**: string|

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
    	"bodyPart": {
    		"id": "1",
    		"part": "leftArm",
    		"problems": [{
    			"id": "1",
    			"problem": "Braço quebrado",
    			"description": "Quebrei meu braço enquanto estava praticando esportes",
    			"occurredDate": "05/05/2012"
    	}
    }
    ```

  * **Code:** 404 Bad Request <br />
      **Content:** `{ error : "Paciente não existene." }`
  * **Code:** 404 Bad Request <br />
      **Content:** `{ error : "Parte do corpo não existente." }`

###Insert
####1. Inserts new bodypart and related problem

| resource            | method         | parameters                              |
|:--------------------|:---------------| ----------------------------------------|
| **/api/patients/:id/bodyparts**      | **POST**       | **part**: string, **problem**: string, **severity**: string,**description**: string, **occurredDate**: string|
*  **URL Params**

   **Required:**
   `id=[string]`
   
*  **Headers**

   **Required:**
   `x-access-token=[valid token received at login]`

**Sample Call**
  ```javascript
  $http.post('/api/patients/1/bodyparts', {
  		"part": "leftArm",
			"problem": "Braço quebrado",
			"description": "Quebrei meu braço enquanto estava praticando esportes",
			"occurredDate": "05/05/2012"
    }).then(success, error);
  ```

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ "success": "true" }`
 
* **Error Response:**

  * **Code:** 404 Bad Request <br />
      **Content:** `{ "error" : "Paciente não existene." }`
    
###Update
####1. Updates a body part and related problem
| resource            | method         | parameters                              |
|:--------------------|:---------------| ----------------------------------------|
| **/api/patients/:id/bodyparts/:id**       | **PUT**       | **part**: string, **problem**: string, **severity**: string,**description**: string, **occurredDate**: string|

*  **URL Params**

   **Required:**
   `id=[string]`
   
*  **Headers**

   **Required:**
   `x-access-token=[valid token received at login]`

**Sample Call**
  ```javascript
  $http.post('/api/patients/1/bodyparts', {
  		"part": "leftArm",
			"problem": "Braço quebrado",
			"description": "Quebrei meu braço enquanto estava praticando esportes",
			"occurredDate": "05/05/2013"
    }).then(success, error);
  ```

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ "success": "true" }`
 
* **Error Response:**

  * **Code:** 404 Bad Request <br />
      **Content:** `{ "error" : "Paciente não existene." }`
