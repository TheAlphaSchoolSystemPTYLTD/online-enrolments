**getStudentUDSetup**
----
	Returns an array of Student UD Setup data in JSON format.
	
* **Version History:**

	TASS v54.4 - Method Added

* **Version:**

	3

* **Permission:**

    Enrolments > Enrolments Setup - Student UD tab - View

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
		"ud": [
			{
				"flag_name": "UD1_FLG",
				"id": 1,
				"flag_value": "",
				"desc": "Interviewed (Prin)",
				"name": "UD1_DESC"
			},
			{
				"flag_name": "UD2_FLG",
				"id": 2,
				"flag_value": "01",
				"desc": "Repeat Year",
				"name": "UD2_DESC"
			},
			...,
			{
				"flag_name": "UD11_FLG",
				"id": 11,
				"lookups": [
					{
						"code": "ARG",
						"desc": "Argyle St"
					},
					{
						"code": "AST",
						"desc": "Asplet Terrace"
					},
					{
						"code": "BH",
						"desc": "Bisbane Home"
					},
					{
						"code": "BWN",
						"desc": "Bowen Hills"
					}
				]
			},
			{
				"flag_name": "UD12_FLG",
				"id": 12,
				"lookups": [
					{
					"code": "USA",
					"desc": "American"
					},
					{
					"code": "AUS",
					"desc": "Australian"
					},
					{
					"code": "BRI",
					"desc": "British"
					}
				]
			},
			...,
			{
				"flag_name": "UD21_FLG",
				"id": 21,
				"flag_value": 21,
				"desc": "Visa Number/Date",
				"name": "UD21_DESC"
			},
			...
		],
		"__tassversion": "01.053.3.000",
		"token": {
			"includelookups": true,
			"timestamp": "{ts '2021-01-19 11:30:43'}"
		}
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
	https://api.tassweb.com.au/tassweb/api/?appcode=DEMOOE&v=2&method=GetStudentUDSetup&token=%2BxYxT3JovxoE2deoaH6feDfyAn%2FcVL0KSCAUjcFpnXM%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="https://api.tassweb.com.au/tassweb/api/">
		<input type="hidden" name="method" value="getStudentUDSetup">
		<input type="hidden" name="appcode" value="DEMOOE">
		<input type="hidden" name="company" value="10">
		<input type="hidden" name="v" value="2">
		<textarea name="token">+xYxT3JovxoE2deoaH6feDfyAn/cVL0KSCAUjcFpnXM=</textarea>
	</form>
	```
