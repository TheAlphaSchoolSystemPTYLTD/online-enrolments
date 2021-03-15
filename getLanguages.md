**getLanguages**
----
	Returns an array of structured language data in JSON format.
	
* **Version History:**

	TASS v54.3 PR2 - Method Added

* **Version:**

	3

* **Permission:**

    Student Records > Student Records Setup > Countries/Languages/ResStatus - View

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
		"languages":[
			{
				"code":9201,
				"desc":"Acholi"
			},
			{
				"code":8601,
				"desc":"Adnymathanha (Yura Ngawarla)"
			},
			{
				"code":9200,
				"desc":"African Languages (Excluding North Africa)"
			}
		],
		"token":{
			"timestamp":"{ts '2021-03-04 12:15:42'}",
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
	http://api.tasscloud.com.au/tassweb/api/?appcode=DEMOOE&v=1&method=GetLanguages&token=3w6XHPP1j163aHf%2FHRAnLA%3D%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		<input type="hidden" name="method" value="GetLanguages" />
		<input type="hidden" name="appcode" value="DEMOOE" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="1" />
		<textarea name="token">3w6XHPP1j163aHf\/HRAnLA==</textarea>
	</form>
	```
