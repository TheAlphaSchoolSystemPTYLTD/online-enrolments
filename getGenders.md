**getGenders**
----
	Returns an array of structured genders data in JSON format.

* **Version History:**

	TASS v53.0 - Method Added

* **Version:**

	3

* **Permission:**

  	Community Plus > Genders Setup - View

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
		"genders": [
			{
				"code": "F",
				"desc": "Female"
			},
			{
				"code": "M",
				"desc": "Male"
			}
		],
		"__tassversion": "01.053.3.000",
		"token": {
			"timestamp": "{ts '2021-01-19 09:37:57'}",
			"codeonly": false
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
	{"codeonly":false}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	http://api.tasscloud.com.au/tassweb/api/?appcode=API04&v=3&method=getGenders&token=3w6XHPP1j163aHf%2FHRAnLA%3D%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		<input type="hidden" name="method" value="getGenders" />
		<input type="hidden" name="appcode" value="API04" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="3" />
		<textarea name="token">3w6XHPP1j163aHf\/HRAnLA==</textarea>
	</form>
	```
