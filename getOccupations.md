**getOccupations**
----
	Returns an array of structured occupation data in JSON format.
	
* **Version History:**

	TASS v54.3 PR2 - Method Added

* **Version:**

	3

* **Permission:**

    Enrolments > Enrolments Setup > Occupations tab - View

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
	{
		"occupations":[
			{
				"code":"ACC",
				"desc":"Accountant"
			},
			{
				"code":"BAR",
				"desc":"Barrister"
			},
			{
				"code":"BUI",
				"desc":"Builder"
			}
		],
		"__tassversion":"01.000.043.0",
		"token":{
			"timestamp":"{ts '2021-03-04 12:16:34'}",
			"codeonly":false
		}
	}
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
