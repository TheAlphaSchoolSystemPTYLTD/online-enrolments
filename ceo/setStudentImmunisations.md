**setStudentImmunisations**
----
  Returns "success" and a count of updated and/or failed immunisation record(s), or a structure of invalid validations messages belonging to immunisation record(s).
  
* **Version History:**

  TASS v57.8.100 - Method Added

* **Version:**

  3

* **Permission:**

  Medical Records > Student Medical > Student Immunisations tab > Edit

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**
 
   `stud_code [string]` - enrolled student code.
 
   `data [array]` - An array of Student Immunisations.
 
   `imm_code [string]` - Immunisation Code required for each record in `data` array.
 
   `imm_year [string]` - Immunisation Year required for each record in `data` array. When updating an existing record, if imm_year provided with empty string, the record will be deleted.

   **Optional:**

   `status_code [string]` - Use existing Immunisation status_code

   `next_due_date [string]` - Next Due Date (Date Format: yyyy-mm-dd)

   **Conditional:**

   `imm_attach_id [string]` - Immunisation Attachment. Field required when air_state_date is provided.

   `air_state_date [string]` - Air State Date (Date Format: yyyy-mm-dd). Field required when imm_attach_id is provided.

   `attachment_file [string]` - field is required where 'attachment_file_name' is supplied. (URLEncoded Format is RECOMMENDED)

   `attachment_file_name [string]` - field is required where 'attachment_file' is supplied.

* **Success Response:**

    ```javascript
    {
      "success":"You successfully saved Enrolled Student Immunisation Status.",
      "__tassversion":"01.054.4.000",
      "token":{
        "stud_code":"0009130",
        "air_state_date":"01/01/2022",
        "timestamp":"{ts '2022-06-27 07:48:03'}",
        "status_code":"AIR",
        "imm_attach_id":{
          "attachment_file_name":"test",
          "attachment_file":"ClRoaXMgaXMgYSB0ZXN0IGZpbGUuCkRvIG5vdCBpbmNsdWRlIGEgdGFibGUhISEKTmFtZQlRdWFudGl0eQlWYWx1ZQppUGFkCTEJNTAwCmlQaG9uZQkxCTEwMDAKVG90YWwJMgkxNTAw"
        }
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

  `data` not supplied or not an array
  ```javascript
  __invalid: {
    "__msg": "'data' IS REQUIRED and must be an Array"
  }
  ```

  `imm_code` not supplied in array
  ```javascript
  __invalid: {
    "__msg": "'imm_code' is required for record [i];"
  }
  ```

  `imm_code`  is not a valid Immunisation Code
  ```javascript
  __invalid: {
    "__msg": "[imm_code] is not a valid Immunisation Code for record [i];"
  }
  ```

  `imm_year` not supplied in array
  ```javascript
  __invalid: {
    "__msg": "'imm_year' is required for record [i];"
  }
  ```

  `imm_year`  is not a valid number
  ```javascript
  __invalid: {
    "__msg": "'imm_year' is not a valid number for record [i];"
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
    "status_code":"AIR",
    "air_state_date":"01/01/2022",
    "imm_attach_id":{
      "attachment_file_name":"test",
      "attachment_file":"ClRoaXMgaXMgYSB0ZXN0IGZpbGUuCkRvIG5vdCBpbmNsdWRlIGEgdGFibGUhISEKTmFtZQlRdWFudGl0eQlWYWx1ZQppUGFkCTEJNTAwCmlQaG9uZQkxCTEwMDAKVG90YWwJMgkxNTAw"
    }
  }
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
    http://api.tasscloud.com.au/tassweb/api/?method=setStudentImmunisations&appcode=API04&company=10&v=3&token=l1D8owEn111IHcXLRwXTB0oU2GX6rj%2BISqa9zXA8We3J3mwgjW5pdUvFK3%2FIZ4mJ4bMyfKTmEoup%2B3tTE9GeLQ%3D%3D
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="setStudentImmunisations">
       <input type="hidden" name="appcode" value="API04">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="3">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We3J3mwgjW5pdUvFK3/IZ4mJ4bMyfKTmEoup+3tTE9GeLQ==</textarea>
    </form>
  ```