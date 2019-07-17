**Most Relevant Terms API**
----
  Returns JSON data on that includes semantically most relevant terms to the queried term

* **URL**

  /topn

* **Method:**

  `POST` 
  
*  **URL Params**

   **Required:**
 
   `userid=[string]` Any string is OK
   `word=[string]`   Term to query

* **Data Params**

  None

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ word : [string], top20 : [(term1_string, rel1_string), ... , (termN_string, relN,string)] }`
    
    `termK_string : string of Kth top relevant term to query term`
    `relN_string : string of relevance of KTh top relevant term to query term`
     
* **Error Response:**

  * **Code:** 200 <br />
    **Content:** `{ error : "xyz does not exist in database" }`

* **Sample Call:**

  ```javascript
  $.ajax({
	url: http://52.221.86.148/api/ideation/concepts + '/topn',
	type: "POST",
	contentType: 'application/json',
	dataType: 'json',
	async: true,
	data: JSON.stringify({"userid":userid, "word": word}),
	success: function(response) {
		console.log(response);

		if (response['error']!=null){
			return (0)
		}
        	topN = response['top20'];
	},
	error: function() {
		return (0)
	}
  });
  ```
