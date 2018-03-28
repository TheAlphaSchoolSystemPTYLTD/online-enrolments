**getStudentUD**
----
	Returns a structure of standard UD data for a student, or extended UD data for the UD area specified in JSON format.

* **Version History:**

    TASS v48.0 - Method Added

* **Version:**

	1

* **Method:**

	`GET | POST`
  
* **Params:**

   **Required:**
 
	`studcode [string]` - Student Code                    

   **Optional:**

	`areacode [integer]` - UD Area Code

   **Conditional:**

	none

* **Success Response:**

    ```javascript
    {
		"ud13_code": "TEN",
		"ud21_text": "Ice Hockey",
		"ud16_code": "",
		"ud4_flg": "N",
		"ud27_text": "",
		"ud24_text": "",
		"ud9_flg": "",
		"ud38_date": "",
		"ud32_date": "",
		"ud19_code": "",
		"ud35_date": "",
		"ud29_text": "",
		"ud26_text": "",
		"ud30_text": "",
		"ud18_code": "",
		"ud23_text": "",
		"ud5_flg": "",
		"ud12_code": "HOC",
		"ud20_code": "",
		"ud15_code": "",
		"ud1_flg": "Y",
		"ud31_date": "",
		"ud34_date": "",
		"ud37_date": "",
		"ud7_flg": "",
		"ud28_text": "",
		"ud6_flg": "",
		"ud10_flg": "",
		"ud22_text": "Water Polo",
		"ud25_text": "",
		"ud14_code": "",
		"ud11_code": "ATH",
		"ud2_flg": "Y",
		"ud3_flg": "Y",
		"ud40_date": "",
		"ud33_date": "",
		"ud8_flg": "",
		"ud17_code": "",
		"ud36_date": "",
		"ud39_date": "",
	}
    ```
 
* **Error Response:**

    `codeonly` not supplied
    ```javascript
    "__msg": "'studcode' IS REQUIRED"
    ```

    `areacode` not a valid integer
    ```javascript
    "__msg": "'areacode' MUST BE AN INTEGER"
    ```
    
* **Sample Parameters:**

	```javascript
	studcode=0009130&areacode=4
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	http://localhost/tassweb/api/?appcode=DEMOOE&v=1&method=GetStudentUD&token=sC%2Bz8gZjKnimKeATtiMMSDam7Skk6OpbUlPoXxxIBko%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://localhost/tassweb/api/">
		<input type="hidden" name="method" value="GetStudentUD" />
		<input type="hidden" name="appcode" value="DEMOOE" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="1" />
		<textarea name="token">sC+z8gZjKnimKeATtiMMSDam7Skk6OpbUlPoXxxIBko=</textarea>
	</form>
	```