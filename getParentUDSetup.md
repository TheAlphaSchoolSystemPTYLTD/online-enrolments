**getParentUDSetup**
----
	Returns an array of Parent UD Setup data in JSON format.
	
* **Version History:**

	TASS v49.3 - Method Added

* **Version:**

	2

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
    "ud": [
		{
			"flag_name": "UD1_FLG",
			"id": 1,
			"flag_value": "",
			"desc": "Active Church Att.",
			"name": "UD1_DESC"
		},
		...,
		{
			"flag_name": "UD11_FLG",
			"id": 11,
			"lookups": [
				{
					"code": "CAN",
					"desc": "Cantonese"
				},
				{
					"code": "ENG",
					"desc": "English"
				},
				{
					"code": "FRE",
					"desc": "French"
				},
				{
					"code": "GER",
					"desc": "German"
				},
				{
					"code": "IND",
					"desc": "Indonesian"
				},
				{
					"code": "NZ",
					"desc": "Kiwi"
				},
				{
					"code": "MAL",
					"desc": "Malaysian"
				},
				{
					"code": "MAN",
					"desc": "Mandarin"
				}
			],
			"flag_value": 11,
			"desc": "Mothers Religion",
			"name": "UD11_DESC"
		},
		...,
		{
			"flag_name": "UD22_FLG",
			"id": 22,
			"flag_value": 21,
			"desc": "Mothers Employer",
			"name": "UD22_DESC"
		}
		...
	]
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
	{"includelookups":"true"}
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