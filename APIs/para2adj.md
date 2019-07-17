**Paragraph to Adjacency API**
----
  Returns JSON data that includes the keywords detected in a paragraph input, and an adjacency matrix including quantified term-term relevancies

* **URL**

  /para2adj

* **Method:**

  `POST` 
  
*  **URL Params**

   **Required:**
 
   `userid=[string]` Any string is OK
   `paragraph=[string]`   Paragraph as a string

* **Data Params**

  None

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ adjacency : [[0, w12, ..., w1N], ... , [w1N, w2N, ..., 0]], keywords : [term1, ..., termN]}`
    
    `termK : string of Kth term in the list of terms in the queried paragraph`<br />
    `wMN : float - quantified relevance between Mth and Nth terms in the list of terms in the queried paragraph`
     
* **Error Response:**

  * **Code:** 200 <br />
    **Content:** `{ error : "JSON Error" }`

* **Sample Call:**

  ```javascript
  $.ajax({
	    url: http://52.221.86.148/api/ideation/concepts + '/para2adj',
	    type: "POST",
	    contentType: 'application/json',
			dataType: 'json',
			async: true,
			data: JSON.stringify({"userid":userid, "paragraph": text}),
			success: function(response) {
				var adj = response['adjacency'];
				var keys = response['keywords'];
	});
  ```
