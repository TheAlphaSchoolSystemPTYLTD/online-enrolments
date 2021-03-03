**getStudentUD**
----
	Returns a structure of standard UD data for a student, or extended UD data for the UD area specified in JSON format.

* **Version History:**

    TASS v55.0 - Method Added

* **Version:**

	3

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
		"ud": {
			"ud13_code": "SUN",
			"ud21_text": 56,
			"ud16_code": "MEN",
			"ud4_flg": "",
			"ud27_text": "",
			"ud24_text": 44,
			"ud9_flg": "",
			"ud38_date": "",
			"ud32_date": "",
			"ud19_code": "TOW",
			"ud35_date": "",
			"ud29_text": "",
			"ud26_text": "",
			"ud30_text": "",
			"ud18_code": "BON",
			"ud23_text": 5678,
			"ud5_flg": "",
			"ud12_code": "052",
			"ud20_code": "MOG",
			"ud15_code": "MP",
			"ud1_flg": "N",
			"ud31_date": "",
			"ud34_date": "",
			"ud37_date": "",
			"ud7_flg": "",
			"ud28_text": "",
			"ud10_flg": "",
			"ud6_flg": "",
			"ud22_text": 567,
			"ud25_text": 12,
			"ud14_code": "NON",
			"ud11_code": 486,
			"ud2_flg": "Y",
			"ud3_flg": "Y",
			"ud40_date": "",
			"ud33_date": "",
			"ud8_flg": "",
			"ud17_code": "MOS",
			"ud36_date": "",
			"ud39_date": "",
			"update_on": ""
		},
		"__status": "success",
		"__tassversion": "01.053.3.000",
		"__invalid": {},
		"__locks": {},
		"token": {
			"areacode": 1,
			"timestamp": "{ts '2021-01-19 10:42:29'}",
			"studcode": "0009096"
		}
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
	{
		"studcode": 20114,
		"areacode": 1
	}
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
