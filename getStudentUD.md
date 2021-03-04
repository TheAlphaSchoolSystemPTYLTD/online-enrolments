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
		"__tassversion":"01.000.043.0",
		"token":{
			"areacode":1,
			"timestamp":"{ts '2021-03-04 12:24:31'}",
			"studcode":"0009999"
		},
		"ud":{
			"ud13_code":"",
			"ud21_text":"",
			"ud16_code":"CIT",
			"ud4_flg":"",
			"ud27_text":"",
			"ud24_text":"",
			"ud9_flg":"",
			"ud38_date":"",
			"ud32_date":"",
			"ud19_code":"",
			"ud35_date":"",
			"ud29_text":"",
			"ud26_text":"",
			"ud30_text":"",
			"ud18_code":"",
			"ud23_text":"",
			"ud5_flg":"",
			"ud12_code":"",
			"ud20_code":"",
			"ud15_code":"",
			"ud1_flg":"N",
			"ud31_date":"2016-03-23 00:00:00.0",
			"ud34_date":"",
			"ud37_date":"",
			"ud7_flg":"",
			"ud28_text":"",
			"ud10_flg":"",
			"ud6_flg":"",
			"ud22_text":"",
			"ud25_text":"",
			"ud14_code":"",
			"ud11_code":"",
			"ud2_flg":"",
			"ud3_flg":"",
			"ud40_date":"",
			"ud33_date":"",
			"ud8_flg":"",
			"ud17_code":"",
			"ud36_date":"",
			"ud39_date":"",
			"update_on":"2019-10-22 14:13:00.0"
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
		"studcode": "0009999",
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
