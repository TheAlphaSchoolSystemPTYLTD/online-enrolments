**getOccupations**
----
	Returns an array of structured occupation data in JSON format.
	
* **Version History:**

	TASS v55.0 - Method Added

* **Version:**

	3

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
    "occupations": [
		{
			"code": "ACC",
			"desc": "Accountant"
		},
		{
			"code": "EM2",
			"desc": "Ambulance / Paramedic"
		},
		{
			"code": "BAR",
			"desc": "Barrister"
		},
		{
			"code": "BUI",
			"desc": "Builder"
		},
		{
			"code": "BUT",
			"desc": "Butcher"
		},
		{
			"code": "DNS",
			"desc": "Dental Nurse"
		},
		{
			"code": "DEN",
			"desc": "Dentist"
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
	{
		"codeonly":"false"
	}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	http://api.tasscloud.com.au/tassweb/api/?appcode=DEMOOE&v=1&method=GetOccupations&token=3w6XHPP1j163aHf%2FHRAnLA%3D%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		<input type="hidden" name="method" value="GetOccupations" />
		<input type="hidden" name="appcode" value="DEMOOE" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="1" />
		<textarea name="token">3w6XHPP1j163aHf\/HRAnLA==</textarea>
	</form>
	```