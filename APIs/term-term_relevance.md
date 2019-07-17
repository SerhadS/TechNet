**Term - Term Relevance API**
----
  Returns JSON data on the quantified relevance of two terms

* **URL**

  /similarity

* **Method:**

  `GET` 
  
*  **URL Params**

   <_If URL params exist, specify them in accordance with name mentioned in URL section. Separate into optional and required. Document data constraints._> 

   **Required:**
 
   `key1=[string]&key2=[string]`

* **Data Params**

  None

* **Success Response:**
  
  <_What should the status code be on success and is there any returned data? This is useful when people need to to know what their callbacks should expect!_>

  * **Code:** 200 <br />
    **Content:** `{ similarity : [float] }`
 
* **Error Response:**

  * **Code:** 200 <br />
    **Content:** `{ error : "term not found" }`

* **Sample Call:**

  `http://52.221.86.148/api/ideation/concepts/similarity?key1=autonomous_vehicle&key2=blind_spot_detecting`
