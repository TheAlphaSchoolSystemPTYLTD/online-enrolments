**getStudentUDSetup**
----
	Returns an array of Student UD Setup data in JSON format.
	
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
			"desc": "Interviewed (Prin)",
			"name": "UD1_DESC"
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
				"code": "BH",
				"desc": "Bisbane Home"
				},
				{
				"code": "BWN",
				"desc": "Bowen Hills"
				},
				{
				"code": "ISP",
				"desc": "Interstate Private"
				},
				{
				"code": "ISG",
				"desc": "Interstate Public"
				},
				{
				"code": "OTH",
				"desc": "Other"
				},
				{
				"code": "STP",
				"desc": "St. Peter's"
				}
			],
			"flag_value": 11,
			"desc": "Campus",
			"name": "UD11_DESC"
		},
		...,
		{
			"flag_name": "UD25_FLG",
			"id": 25,
			"flag_value": "",
			"desc": "Priority Points",
			"name": "UD25_DESC"
		}
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
	https://local.tassweb.net.au/tassweb/api/?appcode=DEMOOE&v=2&method=GetStudentUDSetup&token=%2BxYxT3JovxoE2deoaH6feDfyAn%2FcVL0KSCAUjcFpnXM%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="https://local.tassweb.net.au/tassweb/api/">
		<input type="hidden" name="method" value="getStudentUDSetup">
		<input type="hidden" name="appcode" value="DEMOOE">
		<input type="hidden" name="company" value="10">
		<input type="hidden" name="v" value="2">
		<textarea name="token">+xYxT3JovxoE2deoaH6feDfyAn/cVL0KSCAUjcFpnXM=</textarea>
	</form>
	```