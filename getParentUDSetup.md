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
			"desc": "Active Church Attend",
			"name": "UD1_DESC"
		},
		...,
		{
			"flag_name": "UD11_FLG",
			"id": 11,
			"lookups": [
				{
					"code": "FOO",
					"desc": "Football"
				},
				{
					"code": "GOL",
					"desc": "Golf"
				},
				{
					"code": "HOC",
					"desc": "Hockey"
				},
				{
					"code": "NET",
					"desc": "Netball"
				},
				{
					"code": "RUG",
					"desc": "Rugby"
				},
				{
					"code": "SOC",
					"desc": "Soccer"
				},
				{
					"code": "TEN",
					"desc": "Tennis"
				}
			],
			"flag_value": "",
			"desc": "Sporting Interest",
			"name": "UD11_DESC"
		},
		...,
		{
			"flag_name": "UD25_FLG",
			"id": 25,
			"flag_value": 22,
			"desc": "Employer's Name",
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
	https://local.tassweb.net.au/tassweb/api/?appcode=DEMOOE&v=2&method=GetParentUDSetup&token=%2BxYxT3JovxoE2deoaH6feDfyAn%2FcVL0KSCAUjcFpnXM%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="https://local.tassweb.net.au/tassweb/api/">
		<input type="hidden" name="method" value="getParentUDSetup">
		<input type="hidden" name="appcode" value="DEMOOE">
		<input type="hidden" name="company" value="10">
		<input type="hidden" name="v" value="2">
		<textarea name="token">+xYxT3JovxoE2deoaH6feDfyAn/cVL0KSCAUjcFpnXM=</textarea>
	</form>
	```