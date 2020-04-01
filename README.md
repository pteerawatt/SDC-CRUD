# SDC-CRUD
crud for SDC

**Show Property summary**
----
Return basic house information and contact information to relative agencies

* **URL** /house/:id/info

* **Method:** `GET`
  
*  **URL Params**

   **Required:** `id=[integer]`

* **Data Params** `None`

* **Success Response:**
 
  * **Code:** 200 <br />
    **Content:** `{ id : integer }`
 
* **Error Response:**

  * **Code:** 404 UNAUTHORIZED <br />
    **Content:** `{ error : "Log in" }`

  OR

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "House doesn't exist" }`

* **Sample Call:**
   `axios.get('/house/1')`
  

**Save a new property information**
----
Save the new property info posted by user

* **URL** /house/:id/

* **Method:** `POST`
  
*  **URL Params**

   **Required:** `id = [integer]`

* **Data Params** `{id:interger, info:...}`

* **Success Response:**
 
  * **Code:** 200 <br />
    **Content:** `{ success: 'Successfully posted a new property!' }`
 
* **Error Response:**

  * **Code:** 404 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request" }`

  OR

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "it has been posted" }`

* **Sample Call:**
   `axios.post('/house/1/')`
   

**Update info for the Property**
----
Saved changes by user. 

* **URL** /house/:id/

* **Method:** `PUT`
  
*  **URL Params**

   **Required:** `id = [integer]`

* **Data Params** ` {email: [string], password: [string], id:[string], saved: [boolean]}`

* **Success Response:**
 
  * **Code:** 200 <br />
    **Content:** `{ success : 'Successfully saved the changes you made}`
 
* **Error Response:**

  * **Code:** 404 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`

  OR

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "Property doesn't exist" }`

* **Sample Call:**
   `axios.put('/house/1/')`
   

**Delete Property info**
----
Delete all the information about the property

* **URL** /house/:id/

* **Method:** `DELETE`
  
*  **URL Params**

   **Required:** `id = [integer]`

* **Data Params** `NONE`

* **Success Response:**
 
  * **Code:** 200 <br />
    **Content:** `{ success : 'Successfully deleted the property information' }`
 
* **Error Response:**

  * **Code:** 404 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`

  OR

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "House doesn't exist" }`

* **Sample Call:**
   `axios.delete('/house/1/')`
