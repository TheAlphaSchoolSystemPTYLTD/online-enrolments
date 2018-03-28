**getYearGroups**
----
	Returns an array of structured year group data in JSON format.
	
* **Version History:**

	TASS v49.1 - Method Added

* **Version:**

	1

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
    "yeargroups": [
		{
			"code": -3,
			"desc": "BB"
		},
		{
			"code": -2,
			"desc": "AA"
		},
		{
			"code": -1,
			"desc": "PK"
		},
		{
			"code": 0,
			"desc": "P"
		},
		{
			"code": 1,
			"desc": 1
		},
		{
			"code": 2,
			"desc": 2
		},
		{
			"code": 3,
			"desc": 3
		},
		{
			"code": 4,
			"desc": 4
		},
		{
			"code": 5,
			"desc": 5
		},
		{
			"code": 6,
			"desc": 6
		},
		{
			"code": 7,
			"desc": 7
		},
		{
			"code": 8,
			"desc": 8
		},
		{
			"code": 9,
			"desc": 9
		},
		{
			"code": 10,
			"desc": 10
		},
		{
			"code": 11,
			"desc": 11
		},
		{
			"code": 12,
			"desc": 12
		},
		{
			"code": 13,
			"desc": 13
		}
	]
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
	codeonly=false
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	http://localhost/tassweb/api/?appcode=DEMOOE&v=1&method=GetYearGroups&token=3w6XHPP1j163aHf%2FHRAnLA%3D%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://localhost/tassweb/api/">
		<input type="hidden" name="method" value="GetYearGroups" />
		<input type="hidden" name="appcode" value="DEMOOE" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="1" />
		<textarea name="token">3w6XHPP1j163aHf\/HRAnLA==</textarea>
	</form>
	```