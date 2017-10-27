**getStudentUD**
----
  Returns a structure of standard UD data for a student, or extended UD data for the UD area specified in JSON format.

* **Version:**

  2

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**
 
   `studcode [string]` - Student Code                

   **Optional:**

   `areacode [integer]` - UD Area Code

   **Conditional:**

   none

* **Success Response:**

    ```javascript
      {
		"UD13_CODE": "SOU",
		"UD4_FLG": "Y",
		"UD24_TEXT": "",
		"UD38_DATE": "",
		"UD32_DATE": "2017-05-17 00:00:00.0",
		"UD19_CODE": "",
		"UD29_TEXT": "",
		"UD18_CODE": "",
		"UD23_TEXT": "",
		"UD5_FLG": "",
		"UD12_CODE": 486,
		"UD20_CODE": "",
		"UD34_DATE": "",
		"UD37_DATE": "",
		"UD7_FLG": "",
		"UD6_FLG": "",
		"UD10_FLG": "",
		"UD14_CODE": "NTH",
		"UD11_CODE": "052",
		"UD40_DATE": "",
		"UD8_FLG": "",
		"UD17_CODE": "HOR",
		"UD21_TEXT": "",
		"UD16_CODE": "",
		"UD27_TEXT": "",
		"UD9_FLG": "",
		"UD35_DATE": "",
		"UD26_TEXT": "",
		"UD30_TEXT": "",
		"UD15_CODE": "",
		"UD1_FLG": "",
		"UD31_DATE": "2017-11-23 00:00:00.0",
		"UD28_TEXT": "",
		"UD22_TEXT": "",
		"UD25_TEXT": "",
		"UD2_FLG": "Y",
		"UD3_FLG": "A",
		"UD33_DATE": "2017-05-25 00:00:00.0",
		"UD36_DATE": "",
		"UD39_DATE": "",
		"UPDATE_ON": "2017-05-11 17:23:00.0"
	  }
    ```
 
* **Error Response:**

    `studcode` not supplied
    ```javascript
      "__msg": "'studcode' IS REQUIRED"
    ```

    `areacode` not a valid integer
    ```javascript
      "__msg": "'areacode' MUST BE AN INTEGER"
    ```
    
* **Sample Parameters:**

  ```javascript
    studcode=20087&areacode=1
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
    http://api.tasscloud.com.au/tassweb/api/?method=GetStudentUD&appcode=DEMOOE&company=10&token=UpeKwF%2FsK18NbkgH%2BFGM08gB%2BIMIPBrSSN1qJNA5BJQ%3D
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/api/">
      <input type="hidden" name="method" value="getStudentUD" />
      <input type="hidden" name="appcode" value="DEMOOE" />
      <input type="hidden" name="company" value="10" />
      <textarea name="token">UpeKwF/sK18NbkgH+FGM08gB+IMIPBrSSN1qJNA5BJQ=</textarea>
    </form>
  ```