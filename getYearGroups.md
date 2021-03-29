**getYearGroups**
----
	Returns an array of structured year group data in JSON format.
	
* **Version History:**

	TASS v54.4 - Method Added

* **Version:**

	3

* **Permission:**

    Parent Records > Parent Records Setup - View

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
		"yeargroups":[
			{
				"code":-2,
				"desc":"AA"
			},
			{
				"code":-1,
				"desc":"PK"
			},
			{
				"code":0,
				"desc":"P"
			},
			{
				"code":1,
				"desc":1
			},
			{
				"code":2,
				"desc":2
			},
			{
				"code":3,
				"desc":3
			},
			{
				"code":4,
				"desc":4
			},
			{
				"code":5,
				"desc":5
			}
		],
		"token":{
			"timestamp":"{ts '2021-03-04 12:26:30'}",
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
	http://api.tasscloud.com.au/tassweb/api/?appcode=DEMOOE&v=1&method=GetYearGroups&token=3w6XHPP1j163aHf%2FHRAnLA%3D%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		<input type="hidden" name="method" value="GetYearGroups" />
		<input type="hidden" name="appcode" value="DEMOOE" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="1" />
		<textarea name="token">3w6XHPP1j163aHf\/HRAnLA==</textarea>
	</form>
	```
