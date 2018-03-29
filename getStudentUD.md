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
		"ud13_code": "WST",
		"ud21_text": 840127123,
		"ud16_code": "HAW",
		"ud4_flg": "",
		"ud27_text": "",
		"ud24_text": "",
		"ud9_flg": "",
		"ud38_date": "",
		"ud32_date": "2017-05-27 00:00:00.0",
		"ud19_code": "TOW",
		"ud35_date": "",
		"ud29_text": "",
		"ud26_text": "",
		"ud30_text": "",
		"ud18_code": "MP",
		"ud23_text": "82108301238",
		"ud5_flg": "",
		"ud12_code": "052",
		"ud20_code": "KED",
		"ud15_code": "MP",
		"ud1_flg": "Y",
		"ud31_date": "2017-05-17 00:00:00.0",
		"ud34_date": "",
		"ud37_date": "",
		"ud7_flg": "",
		"ud28_text": "",
		"ud6_flg": "",
		"ud10_flg": "",
		"ud22_text": "",
		"ud25_text": "Mathew Bell",
		"ud14_code": "NTH",
		"ud11_code": 486,
		"ud2_flg": "",
		"ud3_flg": "Y",
		"ud40_date": "",
		"ud33_date": "2018-05-17 00:00:00.0",
		"ud8_flg": "",
		"ud17_code": "MOS",
		"ud36_date": "",
		"ud39_date": ""
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
	studcode=20114&areacode=1
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	http://api.tasscloud.com.au/tassweb/api/?appcode=DEMOOE&v=1&method=GetStudentUD&token=sh4YUZg05q22WN2%2FpPq3bsgB%2BIMIPBrSSN1qJNA5BJQ%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		<input type="hidden" name="method" value="GetStudentUD" />
		<input type="hidden" name="appcode" value="DEMOOE" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="1" />
		<textarea name="token">sh4YUZg05q22WN2\/pPq3bsgB+IMIPBrSSN1qJNA5BJQ=</textarea>
	</form>
	```