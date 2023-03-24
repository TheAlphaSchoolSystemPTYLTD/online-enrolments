**GetStudentUDAreaSetup**
----
	Returns an array of Student UD Setup data in JSON format.
	
* **Version History:**

	TASS v54.4 - Method Added

* **Version:**

	3

* **Permission:**

    Student Records > Student Records Setup > UD Areas tab - View

* **Method:**

	`GET | POST`
  
* **Params:**

   **Required:**
 
	`includelookups [boolean]` - Include lookups

   **Optional:**

	`areacode [string]` - Search for eud fields for this area_code

   **Conditional:**

	none

* **Success Response:**

    ```javascript
	{
		"ud_area": [
				{
					"area_desc": "Restrictions/Privileges",
					"area_code": 8
				},
				{
					"area_desc": "Special Needs",
					"area_code": 9
				},
				{
					"area_desc": "Transport",
					"area_code": 1
				},
				{
					"area_desc": "Parent Access",
					"area_code": 2
				}
		],
		"__tassversion": "01.054.4.000",
		"token": {
			"includelookups": true,
			"timestamp": "{ts '2021-01-19 10:50:06'}"
		}
	}	
	```

    ```javascript
	{
		"ud_area": [
			{
				"eudfld1_desc": "Train pass",
				"area_code": 1,
				"lookups": [],
				"eudfld1_trig": "Y",
				"eudfld1_sort": 1
			},
			{
				"eudfld2_sort": 11,
				"area_code": 1,
				"lookups": [],
				"eudfld2_trig": "Y",
				"eudfld2_desc": "Bus pass"
			},
			{
				"eudfld3_trig": "Y",
				"eudfld3_sort": 2,
				"eudfld3_desc": "Authorised Tpt",
				"area_code": 1,
				"lookups": []
			}
		],
		"__tassversion": "01.054.4.000",
		"areacode": 1,
		"token": {
			"includelookups": true,
			"timestamp": "{ts '2021-01-19 10:53:51'}",
			"area_code": 1
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

	```javascript
	{
		"includelookups":"true",
		"areacode":"1"
	}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	https://api.tassweb.com.au/tassweb/api/?appcode=DIGIENRO&v=2&method=getStudentUDAreaSetup&token=%2BxYxT3JovxoE2deoaH6feDfyAn%2FcVL0KSCAUjcFpnXM%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="https://api.tassweb.com.au/tassweb/api/">
		<input type="hidden" name="method" value="getStudentUDAreaSetup">
		<input type="hidden" name="appcode" value="DIGIENRO">
		<input type="hidden" name="company" value="10">
		<input type="hidden" name="v" value="3">
		<textarea name="token">+xYxT3JovxoE2deoaH6feDfyAn/cVL0KSCAUjcFpnXM=</textarea>
	</form>
	```
