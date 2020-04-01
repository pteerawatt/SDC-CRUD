# SDC-CRUD
crud for SDC

**Show Property summary**
----
Return the targeted house and the neightborhood it is in

* **URL** /api/houses

* **Method:** `GET`
  
*  **URL Params**

   **Required:** `none`

* **Data Params** 
  - if nothing is provided simply return an array of all the houses
  - if { name: <neightborhood name> }
    - will give an array of house objects in the neighborhood
  - if { houseId: <int> }
    - some thing to do with heart??
  

* **Success Response:**
 
  * **Code:** 200 <br />
    **Content:** `{
        "id": int,
        "neighborhood": string,
        "home_cost": int,
        "bedrooms": int,
        "bathrooms": int,
        "home_address": string,
        "sf": int,
        "home_image": .jpg file,
        "heart_filled": 1 || 0
    }`
 
* **Error Response:**

  * **Code:** 404 UNAUTHORIZED <br />
    **Content:** `{ error : "Log in" }`

  OR

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "House doesn't exist" }`

* **Sample Call:**
   `axios.get('/')`
  
**Get neighborhood**
----
Return the neighborhood the property is located in

* **URL** /api/neighborhoods

* **Method:** `GET`
  
*  **URL Params**

   **Required:** `name=[string]`

* **Data Params** `name: <neighborhood name>`

* **Success Response:**
 
  * **Code:** 200 <br />
    **Content:** `{
        "id": int,
        "neighborhood": string,
        "transit_score": int,
        "walk_score": int,
        "value_inc_dec_past": int,
        "value_inc_dec_future": int,
        "median_value": int
    }`
 
* **Error Response:**

  * **Code:** 404 UNAUTHORIZED <br />
    **Content:** `{ error : "Log in" }`

  OR

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "neighborhood doesn't exist" }`

* **Sample Call:**
   `axios.get('/api/neighborhoods?name=The Mission')`
   
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

* **URL** /api/

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
