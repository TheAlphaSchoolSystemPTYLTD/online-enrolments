**setStudentMedical**
----
Returns "success" and a count of updated and/or failed medical record(s), or a structure of invalid validations messages belonging to medical record(s).
  
* **Version History:**

  TASS v57.8.100 - Method Added

* **Version:**

  3

* **Permission:**

  Medical Records > Student Medical > Edit

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**
 
   `stud_code [string]` - enrolled student code.

   **Optional:**

   `mud1-5_flg [string]` - Medical UD flag 1 - 5 ("Y" or "N" only)

   `mud6-10_code [string]` - Medical UD code 6 - 10 (use code in Medical UD Setup)

   `mud11-15_text [string]` - Medical UD text 11 - 15 (text no more than 200 charaters)

   `swim_code [string]` - Use existing swim_code

   **Conditional:**

   None

* **Success Response:**

    ```javascript
    {
      "success":"You successfully saved Enrolled Student Medical Data.",
      "__tassversion":"01.054.4.000",
      "token":{
        "mud11_text":"A+",
        "mud14_text":"",
        "mud1_flg":"Y",
        "mud4_flg":"Y",
        "mud7_code":"MP",
        "mud10_code":"RAK",
        "mud3_flg":"N",
        "mud12_text":"",
        "mud15_text":"",
        "mud9_code":"YES",
        "mud6_code":"WE",
        "stud_code":"0009130",
        "mud13_text":"dd",
        "mud5_flg":"N",
        "timestamp":"{ts '2022-06-27 00:09:50'}",
        "mud2_flg":"N",
        "mud8_code":"ATH"
      }
    }
    ```

* **Error Response:**

  `stud_code` not supplied
  ```javascript
  __invalid: {
    "__msg": "stud_code' IS REQUIRED."
  }
  ```

  `stud_code` not a valid student code in table d3_enrolments
  ```javascript
  __invalid: {
    "stud_code": "Enrolled student not in staging table."
  }
  ```

  `stud_code` not a valid student code in table studenrol
  ```javascript
  __invalid: {
    "stud_code": "Enrolled student not in TASS."
  }
  ```

  `stud_code` is a valid student code in table studenrol where canc_flg = "Y"
  ```javascript
  __invalid: {
    "stud_code": "Enrolled student has been cancelled."
  }
  ```

  `stud_code` is a valid student code in table studenrol where tran_sts = "T"
  ```javascript
  __invalid: {
    "stud_code": "Enrolled student has been transferred to Current."
  }
  ```

  `TO BE ADDED:`

  `mud1-5_flg` "Y" OR "N" only

  `mud5-10_code` "Y" OR "N" only

  `swim_code` validation
    
* **Sample Parameters:**

  ```javascript
  {
    "stud_code":"0009130",
    "mud1_flg":"Y",
    "mud2_flg":"N",
    "mud3_flg":"N",
    "mud4_flg":"Y",
    "mud5_flg":"N",
    "mud6_code":"WE",
    "mud7_code":"MP",
    "mud8_code":"ATH",
    "mud9_code":"YES",
    "mud10_code":"RAK",
    "mud11_text":"A+",
    "mud12_text":"703600060139933770",
    "mud13_text":"dd",
    "mud14_text":"",
    "mud15_text":"",
    "swim_code":"X"
  }
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
    http://api.tasscloud.com.au/tassweb/api/?method=setStudentMedical&appcode=API04&company=10&v=3&token=l1D8owEn111IHcXLRwXTB0oU2GX6rj%2BISqa9zXA8We3J3mwgjW5pdUvFK3%2FIZ4mJ4bMyfKTmEoup%2B3tTE9GeLQ%3D%3D
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="setStudentMedical">
       <input type="hidden" name="appcode" value="API04">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="3">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We3J3mwgjW5pdUvFK3/IZ4mJ4bMyfKTmEoup+3tTE9GeLQ==</textarea>
    </form>
  ```