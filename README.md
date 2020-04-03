# SDC-CRUD
crud for SDC

**Get targethouse houses**
----
Return information bout the target house

* **URL** /api/houses/`houseId`

* **Method:** `GET`
  
*  **URL Params**

   **Required:** `none`

* **Data Params** 
  - none
  

* **Success Response:**
 
  * **Code:** 200 <br />
    **Content:** an array of house objects: 
    [{
        "id": int,
        "neighborhood": string,
        "home_cost": int,
        "bedrooms": int,
        "bathrooms": int,
        "home_address": string,
        "sf": int,
        "home_image": .jpg file,
        "heart_filled": 1 || 0
    }. . .]
 
* **Error Response:**

  * **Code:** 404 UNAUTHORIZED <br />
    **Content:** `{ error : "Please Log in" }`

  OR

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "No houses are found" }`

* **Sample Call:**
   `axios.get('/api/houses/1')`
  
**Get all the houses in the neighborhood**
----
Return all the houses in the neighborhood

* **URL** /api/houses/`houseId`/neighborhood

* **Method:** `GET`
  
*  **URL Params**

   **Required:** `none`

* **Data Params** 

  `{ name: <neightborhood name> }`
  
* **Success Response:**
 
  * **Code:** 200 <br />
    **Content:** an array of house objects: [{
        "id": int,
        "neighborhood": string,
        "home_cost": int,
        "bedrooms": int,
        "bathrooms": int,
        "home_address": string,
        "sf": int,
        "home_image": .jpg file,
        "heart_filled": 1 || 0
    }. . .]
 
* **Error Response:**

  * **Code:** 404 UNAUTHORIZED <br />
    **Content:** `{ error : "Please Log in" }`

  OR

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "No houses in this neighborhood" }`

* **Sample Call:**
   `axios.get('/api/houses/1/neighborhood')`
   
**Get like status**
----
Return the liked status of a home

* **URL** /api/houses/`houseId`/likes

* **Method:** `GET`
  
*  **URL Params** 

   **Required:** `none`

* **Data Params** 

  `{ houseId: <int> }`

* **Success Response:**
 
  * **Code:** 200 <br />
    **Content:** an array of house objects: `[{ "heart_filled": 1 || 0 }]`
 
* **Error Response:**

  * **Code:** 404 UNAUTHORIZED <br />
    **Content:** `{ error : "Please Log in" }`

  OR

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "No houses are found" }`

* **Sample Call:**
   `axios.get('/api/houses/1/likes')`
   
**Get the neighborhood**
----
Returns information on the neighborhood

* **URL** /api/neighborhoods

* **Method:** `GET`
  
*  **URL Params**

   **Required:** ``

* **Data Params** `name: <neighborhood name>`

* **Success Response:**
 
  * **Code:** 200 <br />
    **Content:** {
        "id": int,
        "neighborhood": string,
        "transit_score": int,
        "walk_score": int,
        "value_inc_dec_past": int,
        "value_inc_dec_future": int,
        "median_value": int
    }
 
* **Error Response:**

  * **Code:** 404 UNAUTHORIZED <br />
    **Content:** `{ error : "Log in" }`

  OR

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "neighborhood doesn't exist" }`

* **Sample Call:**
   `axios.get('/api/neighborhoods')`
   
**Create a new House**
----
Create a new house

* **URL** /api/houses/create

* **Method:** `POST`
  
*  **URL Params**

   **Required:** ``

* **Data Params** all the params from the house object

* **Success Response:**
 
  * **Code:** 200 <br />
    **Content:** `{ success: 'Successfully listed a new hoe' }`
 
* **Error Response:**

  * **Code:** 404 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request" }`

* **Sample Call:**
   `axios.post('/api/houses/create')`
   
**Delete a home**
----
Delete a home

* **URL** /api/houses/delete/`houseId`

* **Method:** `DELETE`
  
*  **URL Params**

   **Required:** `id = [integer]`

* **Data Params** `{ houseId: int }`

* **Success Response:**
 
  * **Code:** 200 <br />
    **Content:** `{ success : 'Successfully deleted the house' }`
 
* **Error Response:**

  * **Code:** 404 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`

  OR

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "house doesn't exist" }`

* **Sample Call:**
   `axios.delete('/api/houses/delete/1')`

**Update liked status**
----
update the like status of the house

* **URL** /api/houses/`houseId`/likes

* **Method:** `PATCH`
  
*  **URL Params**

   **Required:** `houseId = [integer]`

* **Data Params** `{houseId: int}`

* **Success Response:**
 
  * **Code:** 200 <br />
    **Content:** `{ success : 'Successfully liked}`
 
* **Error Response:**

  * **Code:** 404 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`

  OR

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "Property doesn't exist" }`

* **Sample Call:**
   `axios.put('/api/houses/1/likes')`
   


