**getTree API**
----
  Returns JSON data that includes the data of a tree graph having queried term as the root node
  
* **URL**

  /getTree

* **Method:**

  `POST` 
  
*  **URL Params**

   **Required:**
 
   `userid=[string]` Any string is OK <br />
   `word=[string]`   Query term

* **Data Params**

  None

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ nodes : [{name: n0_string, group:0}, ..., {name: n39_string, group:3}], links: [{source :0, target:1, weight:1}, ..., {source:12, target:39, weight:1}]}`
    
    `nK_string : string of Kth term in the list of terms in the tree`<br />
     
* **Error Response:**

  * **Code:** 200 <br />
    **Content:** `{ error : "JSON Error" }`

* **Sample Call:**

  ```javascript
  $.ajax({
  	url: http://52.221.86.148/api/ideation/concepts + '/getTree',
	type: "POST",
	contentType: 'application/json',
	dataType: 'json',
	async: true,
	data: JSON.stringify({"userid":userid, "word": word}),
	success: function(response) {
        var graph_data = response;
	},
	});
  ```
