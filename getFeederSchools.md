**getFeederSchools**
----
	Returns an array of structured feeder school data in JSON format.
	
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
    "schools": [
		{
			"region_desc": "Melbourne City",
			"code": "BALCC",
			"region_code": "MELC",
			"tass_cmpy_code_desc": "",
			"export_code": "",
			"tass_cmpy_code": "",
			"desc": "Ballarat Christian College"
		},
		{
			"region_desc": "",
			"code": "BSH",
			"region_code": "",
			"tass_cmpy_code_desc": "",
			"export_code": "",
			"tass_cmpy_code": "",
			"desc": "Brisbane State High School"
		},
		{
			"region_desc": "Bundaberg Cluster",
			"code": "BUNDC",
			"region_code": "BUND",
			"tass_cmpy_code_desc": "",
			"export_code": "",
			"tass_cmpy_code": "",
			"desc": "Bundaberg Christian School"
		},
		{
			"region_desc": "",
			"code": "EVT",
			"region_code": "",
			"tass_cmpy_code_desc": "",
			"export_code": "",
			"tass_cmpy_code": "",
			"desc": "Everton Highxx"
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
	http://localhost/tassweb/api/?appcode=DEMOOE&v=1&method=GetFeederSchools&token=3w6XHPP1j163aHf%2FHRAnLA%3D%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://localhost/tassweb/api/">
		<input type="hidden" name="method" value="GetFeederSchools" />
		<input type="hidden" name="appcode" value="DEMOOE" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="1" />
		<textarea name="token">3w6XHPP1j163aHf\/HRAnLA==</textarea>
	</form>
	```