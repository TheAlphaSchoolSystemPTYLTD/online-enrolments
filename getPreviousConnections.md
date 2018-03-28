**getPreviousConnections**
----
	Returns an array of structured previous connection data in JSON format.
	
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
    "connections": [
		{
			"code": "BR",
			"desc": "Brother in School"
		},
		{
			"code": "N",
			"desc": "None"
		},
		{
			"code": "PS",
			"desc": "Parent Past Student"
		},
		{
			"code": "SC",
			"desc": "Scholarship"
		},
		{
			"code": "SI",
			"desc": "Sister in School"
		},
		{
			"code": "TC",
			"desc": "Teacher in School"
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
	http://localhost/tassweb/api/?appcode=DEMOOE&v=1&method=GetPreviousConnections&token=3w6XHPP1j163aHf%2FHRAnLA%3D%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://localhost/tassweb/api/">
		<input type="hidden" name="method" value="GetPreviousConnections" />
		<input type="hidden" name="appcode" value="DEMOOE" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="1" />
		<textarea name="token">3w6XHPP1j163aHf\/HRAnLA==</textarea>
	</form>
	```