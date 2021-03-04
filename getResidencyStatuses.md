**getResidencyStatuses**
----
	Returns an array of structured residency status data in JSON format.
	
* **Version History:**

	TASS v55.0- Method Added

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
	{
		"__tassversion":"01.000.043.0",
		"token":{
			"timestamp":"{ts '2021-03-04 12:21:07'}",
			"codeonly":false
		},
		"statuses":[
			{
				"census_flg":"Y",
				"code":"AUS",
				"expcode":"XXXX34",
				"citizen_flg":"Y",
				"permres_flg":"N",
				"res_exp_code":"XXXX34",
				"desc":"Australian Citizen"
			},
			{
				"census_flg":"Y",
				"code":"PR",
				"expcode":"",
				"citizen_flg":"N",
				"permres_flg":"Y",
				"res_exp_code":"",
				"desc":"Australian Permanent Resident"
			}
		]
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
	http://api.tasscloud.com.au/tassweb/api/?appcode=DEMOOE&v=1&method=GetResidencyStatuses&token=3w6XHPP1j163aHf%2FHRAnLA%3D%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		<input type="hidden" name="method" value="GetResidencyStatuses" />
		<input type="hidden" name="appcode" value="DEMOOE" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="1" />
		<textarea name="token">3w6XHPP1j163aHf\/HRAnLA==</textarea>
	</form>
	```
