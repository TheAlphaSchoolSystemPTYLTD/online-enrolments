**setStudentImmunisationRegister**
----
  Returns "success" and a count of updated and/or failed immunisation register record(s), or a structure of invalid validations messages belonging to immunisation register record(s).
  
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

   **Optional:**

   `status_code [string]` - Use existing Immunisation status_code

   `next_due_date [string]` - Next Due Date (Date Format: yyyy-mm-dd)

   **Conditional:**

   `imm_attach_id [string]` - Immunisation Attachment. Field required when air_state_date is provided.

   `air_state_date [string]` - Air State Date (Date Format: yyyy-mm-dd). Field required when imm_attach_id is provided.

   `attachment_file [string]` - field is required where 'attachment_file_name' is supplied for each item in 'attachments'. (URLEncoded Format is RECOMMENDED)

   `attachment_file_name [string]` - field is required where 'attachment_file' is supplied for each item in 'attachments'.

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

  `imm_attach_id` [string] is empty, or only one of attachment_file and attachment_file_name is passed in
  ```javascript
  __invalid: {
    "[field]": "attachment_file and attachment_file_name are required if [field] is passed in."
  }
  ```

  `imm_attach_id` [string] attachment_file is passed in but attachment_file_name is not passed in
  ```javascript
  __invalid: {
    "attachment_file_name": "attachment_file_name field is required where 'attachment_file' is supplied."
  }
  ```

  `imm_attach_id` [string] attachment_file_name is passed in but attachment_file is not passed in
  ```javascript
  __invalid: {
    "attachment_file": "attachment_file field is required where 'attachment_file_name' is supplied."
  }
  ```

  `imm_attach_id` [string] attachment_file_name exceeds 255 characters
  ```javascript
  __invalid: {
    "attachment_file_name": "attachment_file_name must be between 1 and 255 characters."
  }
  ```

  `status_code` not a valid status_code
  ```javascript
  __invalid: {
    "status_code": "status_code is not a valid Immunisation Status."
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
    http://api.tasscloud.com.au/tassweb/api/?method=setStudentImmunisationRegister&appcode=API04&company=10&v=3&token=l1D8owEn111IHcXLRwXTB0oU2GX6rj%2BISqa9zXA8We3J3mwgjW5pdUvFK3%2FIZ4mJ4bMyfKTmEoup%2B3tTE9GeLQ%3D%3D
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="setStudentImmunisationRegister">
       <input type="hidden" name="appcode" value="API04">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="3">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We3J3mwgjW5pdUvFK3/IZ4mJ4bMyfKTmEoup+3tTE9GeLQ==</textarea>
    </form>
  ```