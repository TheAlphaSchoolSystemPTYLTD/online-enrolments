**getCampuses**
----
	Returns an array of structured campus data in JSON format.

* **Version History:**

	TASS v49.1 - Method Added

* **Version:**

	1

* **Method:**

	`GET | POST`
  
* **Params:**

   **Required:**
 
	`codeonly [boolean]` - Return Code only. Must be 'true' or 'false'.                    

   **Optional:**

	none

   **Conditional:**

	none

* **Success Response:**

    ```javascript
    "campuses": [
		{
			"code": "ARG",
			"desc": "Argyle Street Campus"
		},
		{
			"code": "D5W",
			"desc": "De Five Warders Campus"
		},
		{
			"code": "JU",
			"desc": "Junior School (Billabong Road)"
		},
		{
			"code": "JUS",
			"desc": "Just made it up campus with 12"
		},
		{
			"code": "SE",
			"desc": "Senior School (Curlew St)"
		},
		{
			"code": "THO",
			"desc": "Thompson Street Campus"
		},
		{
			"code": "ZZZ",
			"desc": "Banana Cmpy 10 Campus"
		}
	]
    ```
 
* **Error Response:**

    `codeonly` not supplied
    ```javascript
    "__msg": "'codeonly' IS REQUIRED"
    ```

    `codeonly` invalid
    ```javascript
    "__msg": "'codeonly' MUST BE 'true' or 'false'"
    ```
    
* **Sample Parameters:**

	```javascript
	codeonly=false
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	http://localhost/tassweb/api/?appcode=DEMOOE&v=1&method=GetCampuses&token=3w6XHPP1j163aHf%2FHRAnLA%3D%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://localhost/tassweb/api/">
		<input type="hidden" name="method" value="getCampuses" />
		<input type="hidden" name="appcode" value="DEMOOE" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="1" />
		<textarea name="token">3w6XHPP1j163aHf\/HRAnLA==</textarea>
	</form>
	```