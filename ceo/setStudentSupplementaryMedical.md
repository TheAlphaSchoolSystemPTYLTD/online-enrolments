**setStudentSupplementaryMedical**
----
  Returns "success" and a count of updated and/or failed supplementary medical record(s), or a structure of invalid validations messages belonging to supplementary medical record(s).
  
* **Version History:**

  TASS v57.8.100 - Method Added

* **Version:**

  3

* **Permission:**

  Medical Records > Student Medical > Supplementary Info tab > Edit

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**
 
   `stud_code [string]` - enrolled student code.
 
   `msupp_code [string]` - use existing medical supplementary code.
 
   **Optional:**
 
   `comm_text [string]` - comment (additional details 200 characters maximum).

   **Conditional:**

   None

* **Success Response:**

    ```javascript
    {
      "success":"You successfully saved Enrolled Student Medical Supplementary Information.",
      "__tassversion":"01.054.4.000",
      "token":{
        "stud_code":"0009130",
        "msupp_code":"DEN",
        "timestamp":"{ts '2022-06-27 12:20:08'}",
        "comm_text":"test comment"
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

  `msupp_code` does not exist in practitioner type setup
  ```javascript
  __invalid: {
    "[msupp_code]": "Supplementary Code does not exist."
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
    
* **Sample Parameters:**

  ```javascript
  {
    "stud_code":"0009130",
    "msupp_code":"DEN",
    "comm_text":"test comment"
  }
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
    http://api.tasscloud.com.au/tassweb/api/?method=setStudentSupplementaryMedical&appcode=API04&company=10&v=3&token=l1D8owEn111IHcXLRwXTB0oU2GX6rj%2BISqa9zXA8We3J3mwgjW5pdUvFK3%2FIZ4mJ4bMyfKTmEoup%2B3tTE9GeLQ%3D%3D
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="setStudentSupplementaryMedical">
       <input type="hidden" name="appcode" value="API04">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="3">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We3J3mwgjW5pdUvFK3/IZ4mJ4bMyfKTmEoup+3tTE9GeLQ==</textarea>
    </form>
  ```