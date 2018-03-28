**getParentUD**
----
	Returns a structured parent UD data in JSON format.
	
* **Version History:**

	TASS v49.1 - Method Added

* **Version:**

	1

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
		"ud13_code": "AU",
		"ud21_text": "Medibank Private",
		"ud16_code": "EDU",
		"ud4_flg": "Y",
		"ud24_text": "HIGH_SUITABLE",
		"ud9_flg": "",
		"ud19_code": "FRI",
		"ud18_code": "DR",
		"ud23_text": "Wheel Whistler",
		"ud5_flg": "Y",
		"ud12_code": "ROW",
		"ud15_code": 1,
		"ud20_code": "FAC",
		"ud1_flg": "Y",
		"ud7_flg": "H",
		"ud6_flg": "H",
		"ud10_flg": "Y",
		"ud22_text": "Cyc'd for Bikes",
		"ud25_text": "",
		"ud14_code": "AUS",
		"ud11_code": "CAN",
		"ud2_flg": "N",
		"ud3_flg": "Y",
		"ud8_flg": "Y",
		"ud17_code": "DR"
	}
    ```
 
* **Error Response:**

    `codeonly` not supplied
    ```javascript
    "__msg": "'parcode' IS REQUIRED"
    ```
    
* **Sample Parameters:**

	```javascript
	parcode=000055
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	http://localhost/tassweb/api/?appcode=DEMOOE&v=1&method=GetParentUD&token=GYdZUneRNspdwvlEwsnwUA%3D%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://localhost/tassweb/api/">
		<input type="hidden" name="method" value="GetParentUD" />
		<input type="hidden" name="appcode" value="DEMOOE" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="1" />
		<textarea name="token">GYdZUneRNspdwvlEwsnwUA==</textarea>
	</form>
	```