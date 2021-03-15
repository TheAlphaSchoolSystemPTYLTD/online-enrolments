**getParentUDSetup**
----
	Returns an array of Parent UD Setup data in JSON format.
	
* **Version History:**

	TASS v54.3 PR2 - Method Added

* **Version:**

	3

* **Permission:**

    Enrolments > Enrolments Setup > Parent UD tab - View

* **Method:**

	`GET | POST`
  
* **Params:**

   **Required:**
 
	`includelookups [boolean]` - Include lookups                    

   **Optional:**

	none

   **Conditional:**

	none

* **Success Response:**

    ```javascript
	{
		"__tassversion":"01.000.043.0",
		"token":{
			"includelookups":true,
			"timestamp":"{ts '2021-03-04 12:17:49'}"
		},
		"ud":[
			{
				"flag_name":"UD1_FLG",
				"id":1,
				"flag_value":"",
				"desc":"Active Church Attend",
				"name":"UD1_DESC"
			},
			{
				"flag_name":"UD11_FLG",
				"id":11,
				"lookups":[
					{
						"code":"CRI",
						"desc":"Cricket Match"
					},
					{
						"code":"DEB",
						"desc":"Debating"
					}
				],
				"flag_value":"",
				"desc":"Sport Interest",
				"name":"UD11_DESC"
			}
		]
	}
    ```
 
* **Error Response:**

    Required `includelookups` not supplied.
	```javascript
	"__invalid": {
		"includelookups": "field is required"
	}
	```
	
	Bool `includelookups` not a valid bool.
	```javascript
	"__invalid": {
		"includelookups": "Value is not a valid boolean."
	}
	```
    
* **Sample Parameters:**

	```javascript
	{
		"includelookups":"true"
	}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	https://api.tassweb.com.au/tassweb/api/?appcode=DEMOOE&v=2&method=GetParentUDSetup&token=%2BxYxT3JovxoE2deoaH6feDfyAn%2FcVL0KSCAUjcFpnXM%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="https://api.tassweb.com.au/tassweb/api/">
		<input type="hidden" name="method" value="getParentUDSetup">
		<input type="hidden" name="appcode" value="DEMOOE">
		<input type="hidden" name="company" value="10">
		<input type="hidden" name="v" value="2">
		<textarea name="token">+xYxT3JovxoE2deoaH6feDfyAn/cVL0KSCAUjcFpnXM=</textarea>
	</form>
	```
