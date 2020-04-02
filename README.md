# SDC-CRUD
crud for SDC

**Get all the houses**
----
Return all the houses in the database

* **URL** /api/houses

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
   `axios.get('/')`
  
**Get all the houses in the neighborhood**
----
Return all the houses in the neighborhood

* **URL** /api/houses

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
   `axios.get('/')`
   
**Get like status**
----
Return the liked status of all the homes

* **URL** /api/houses

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
   `axios.get('/')`
   
**Get the neighborhood**
----
Returns information on the neighborhood

* **URL** /api/neighborhoods

* **Method:** `GET`
  
*  **URL Params**

   **Required:** `name=[string]`

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
   `axios.get('/api/neighborhoods?name=The Mission')`
   
**Post Comments**
----
Post a comment on a house

* **URL** /api/house/comment

* **Method:** `POST`
  
*  **URL Params**

   **Required:** `id = [integer]`

* **Data Params** `{id: <interger>, comment: <string>}`

* **Success Response:**
 
  * **Code:** 200 <br />
    **Content:** `{ success: 'Successfully posted a comment!' }`
 
* **Error Response:**

  * **Code:** 404 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request" }`

* **Sample Call:**
   `axios.post('/house/comment/1')`
   
**Delete comment**
----
Delete a comment on the house

* **URL** /api/house/comment

* **Method:** `DELETE`
  
*  **URL Params**

   **Required:** `id = [integer]`

* **Data Params** `NONE`

* **Success Response:**
 
  * **Code:** 200 <br />
    **Content:** `{ success : 'Successfully deleted the comment' }`
 
* **Error Response:**

  * **Code:** 404 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`

  OR

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "comment doesn't exist" }`

* **Sample Call:**
   `axios.delete('/house/comment/1')`

**Update liked status**
----
Saved changes by user. 

* **URL** /api/houses

* **Method:** `PUT`
  
*  **URL Params**

   **Required:** `houseId = [integer]`

* **Data Params** `{houseId: id}`

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
   `axios.put('/houses/1/')`
   


