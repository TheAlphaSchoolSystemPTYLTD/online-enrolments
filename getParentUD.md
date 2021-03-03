**getParentUD**
----
	Returns a structured parent UD data in JSON format.
	
* **Version History:**

	TASS v55.0 - Method Added

* **Version:**

	3

* **Method:**

	`GET | POST`
  
* **Params:**

   **Required:**
 
	`parcode [string]` - Parent Code                    

   **Optional:**

	none

   **Conditional:**

	none

* **Success Response:**

    ```javascript
	{
		"ud": {
			"ud13_code": "",
			"ud21_text": "",
			"ud16_code": "",
			"ud4_flg": "",
			"ud24_text": "",
			"ud9_flg": "",
			"ud19_code": "",
			"ud18_code": "",
			"ud23_text": "",
			"ud5_flg": "",
			"ud12_code": "",
			"ud15_code": "",
			"ud20_code": "",
			"ud1_flg": "",
			"ud7_flg": "",
			"ud6_flg": "",
			"ud10_flg": "",
			"ud22_text": "",
			"ud25_text": "",
			"ud14_code": "",
			"ud11_code": "",
			"ud2_flg": "",
			"ud3_flg": "",
			"ud8_flg": "",
			"ud17_code": ""
		},
		"__status": "success",
		"__tassversion": "01.053.3.000",
		"__invalid": {},
		"__locks": {},
		"token": {
			"timestamp": "{ts '2021-01-19 09:42:13'}",
			"parcode": 10040
		}
	}
    ```
 
* **Error Response:**

    `codeonly` not supplied
    ```javascript
    "__msg": "'parcode' IS REQUIRED"
    ```
    
* **Sample Parameters:**

	```javascript
	{
		"parcode":10040
	}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	http://api.tasscloud.com.au/tassweb/api/?appcode=DEMOOE&v=1&method=GetParentUD&token=L%2BApeTngUJMNLPgXuxoPUg%3D%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		<input type="hidden" name="method" value="GetParentUD" />
		<input type="hidden" name="appcode" value="DEMOOE" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="1" />
		<textarea name="token">L+ApeTngUJMNLPgXuxoPUg==</textarea>
	</form>
	```
