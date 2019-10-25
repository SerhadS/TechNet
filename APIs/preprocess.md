**Preprocess API**
----
  Returns JSON data that includes the preprocessed and word tokenized paragraph

* **URL**

  /preprocess

* **Method:**

  `POST` 
  
*  **URL Params**

   **Required:**
 
   `userid=[string]` Any string is OK <br />
   `paragraph=[string]`   Paragraph as a string

* **Data Params**

  None

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ processed : [[sent1_term1, ..., sent1_termN], ..., [sentM_term1, ..., sentM_termK]]}`
    
    `sentM_termK : string of Kth term in the Mth sentence in the paragraph`<br />
     
* **Error Response:**

  * **Code:** 200 <br />
    **Content:** `{ error : "JSON Error" }`
  * **Code:** 200 <br />
    **Content:** `{ error : 'error':'Too long! Max word count allowed for this API is 1000' }`
* **Sample Call:**

  ```javascript
  $.ajax({
	    url: http://52.221.86.148/api/ideation/concepts + '/preprocess',
	    type: "POST",
	    contentType: 'application/json',
			dataType: 'json',
			async: true,
			data: JSON.stringify({"userid":userid, "paragraph": text}),
			success: function(response) {
				var preprocessed_text = response['processed'];
	});
  ```
