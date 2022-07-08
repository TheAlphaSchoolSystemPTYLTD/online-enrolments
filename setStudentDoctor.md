**setStudentDoctor**
----
  Returns "success" and a count of updated and/or failed medical record(s), or a structure of invalid validations messages belonging to medical record(s).
  
* **Version History:**

  TASS v57.8.100 - Method Added

* **Version:**

  3

* **Permission:**

  Medical Records > Student Medical > Practitioners tab > Edit

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**
 
   `stud_code [string]` - enrolled student code.
 
   `ptype_code [string]` - use existing practitioner type code.
 
   `doct_name [string]` - practitioner name (30 characters maximum).

   **Optional:**
 
   `prac_num [string]` - prac_num, when provided and an existing doctor found, program will edit the doctor with data provided, otherwise it will add a new doctor.

   **Conditional:**

   None

* **Success Response:**

    ```javascript
    {
      "success":"You successfully saved Enrolled Student Doctor.",
      "__tassversion":"01.054.4.000",
      "token":{
        "stud_code":"0009130",
        "timestamp":"{ts '2022-06-27 12:14:04'}",
        "ptype_code":"003",
        "doct_name":"Dr Alexander Sebasti Millhouse",
        "prac_num":2
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

  `ptype_code` does not exist in practitioner type setup
  ```javascript
  __invalid: {
    "[ptype_code]": "Practitioner Type does not exist."
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

  `doct_name` exceed 30 characters
  ```javascript
  __invalid: {
    "doct_name": "exceed 30 characters."
  } 
  ```
    
* **Sample Parameters:**

  ```javascript
  {
    "stud_code":"0009130",
    "ptype_code":"003",
    "doct_name":"Dr Alexander Sebasti Millhouse",
    "prac_num":"2"
  }
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
    http://api.tasscloud.com.au/tassweb/api/?method=setStudentDoctor&appcode=API04&company=10&v=3&token=l1D8owEn111IHcXLRwXTB0oU2GX6rj%2BISqa9zXA8We3J3mwgjW5pdUvFK3%2FIZ4mJ4bMyfKTmEoup%2B3tTE9GeLQ%3D%3D
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="setStudentDoctor">
       <input type="hidden" name="appcode" value="API04">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="3">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We3J3mwgjW5pdUvFK3/IZ4mJ4bMyfKTmEoup+3tTE9GeLQ==</textarea>
    </form>
  ```