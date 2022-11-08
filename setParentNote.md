**setParentNote**
----
  Returns "success" and a count of updated and/or failed parent notes record(s), or a structure of invalid validations messages belonging to parent notes record(s).
  
* **Version History:**

  TASS v57.8.100 - Method Added

* **Version:**

  3

* **Permission:**

  Parent Records > Parent Information > Parents > Notes tab > Add

* **Method:**

  `GET | POST`
  
* **Params:**

  **Required:**
 
  `par_code [string]` - Parent Code

  `note_date [date]` - Standard Note Date

  `note_cat [string]` - Standard Note Category Code

  `note_text [string]` - Standard Note Text

  **Optional:**

  `note_attach_id [string]` - Standard Note Attachment.

  **Conditional:**

  `attachment_file [string]` - Base64 Encoded. Field is required where 'attachment_file_name' is supplied. (URLEncoded Format is RECOMMENDED).

  `attachment_file_name [string]` - Field is required where 'attachment_file' is supplied.

* **Success Response:**

  ```javascript
  {
    "success":"You successfully saved Enrolled Parent  Note.",
    "__tassversion":"01.054.4.000",
    "token":{
      "note_date":"16/06/2022",
      "par_code":"000055",
      "attachments":{
        "attachment_file_name":"test",
        "attachment_file":"ClRoaXMgaXMgYSB0ZXN0IGZpbGUuCkRvIG5vdCBpbmNsdWRlIGEgdGFibGUhISEKTmFtZQlRdWFudGl0eQlWYWx1ZQppUGFkCTEJNTAwCmlQaG9uZQkxCTEwMDAKVG90YWwJMgkxNTAw"
      },
      "timestamp":"{ts '2022-06-27 12:37:04'}",
      "note_text":"note text test",
      "note_cat":"GEN"
    }
  }
  ```

* **Error Response:**

  `par_code` not supplied
  ```javascript
  __invalid: {
    "__msg": "par_code' is required."
  }
  ```

  `note_date` not supplied
  ```javascript
  __invalid: {
    "__msg": "note_date' is required."
  }
  ```

  `note_cat` not supplied
  ```javascript
  __invalid: {
    "__msg": "note_cat' is required."
  }
  ```

  `note_text` not supplied
  ```javascript
  __invalid: {
    "__msg": "note_text' is required."
  }
  ```

  `note_cat` does not exist in practitioner type setup
  ```javascript
  __invalid: {
    "[note_cat]": "Note Category does not exist."
  }
  ```

  `note_text` over 4000 characters
  ```javascript
  __invalid: {
    "note_text": "'note_text' exceeded 4000 characters."
  }
  ```

  `note_attach_id` [string] is empty, or only one of attachment_file and attachment_file_name is passed in
  ```javascript
  __invalid: {
    "[field]": "attachment_file and attachment_file_name are required if [field] is passed in."
  }
  ```

  `note_attach_id` [string] attachment_file is passed in but attachment_file_name is not passed in
  ```javascript
  __invalid: {
    "attachment_file_name": "attachment_file_name field is required where 'attachment_file' is supplied."
  }
  ```

  `note_attach_id` [string] attachment_file_name is passed in but attachment_file is not passed in
  ```javascript
  __invalid: {
    "attachment_file": "attachment_file field is required where 'attachment_file_name' is supplied."
  }
  ```

  `note_attach_id` [string] attachment_file_name exceeds 255 characters
  ```javascript
  __invalid: {
    "attachment_file_name": "attachment_file_name must be between 1 and 255 characters."
  }
  ```
    
* **Sample Parameters:**

  ```javascript
  {
    "par_code":"000055",
    "note_date":"16/06/2022",
    "note_cat":"GEN",
    "note_text":"note text test",
    "attachments":{
        "attachment_file_name":"test",
        "attachment_file":"ClRoaXMgaXMgYSB0ZXN0IGZpbGUuCkRvIG5vdCBpbmNsdWRlIGEgdGFibGUhISEKTmFtZQlRdWFudGl0eQlWYWx1ZQppUGFkCTEJNTAwCmlQaG9uZQkxCTEwMDAKVG90YWwJMgkxNTAw"
    }
  }
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
    http://api.tasscloud.com.au/tassweb/api/?method=setParentNote&appcode=API04&company=10&v=3&token=l1D8owEn111IHcXLRwXTB0oU2GX6rj%2BISqa9zXA8We3J3mwgjW5pdUvFK3%2FIZ4mJ4bMyfKTmEoup%2B3tTE9GeLQ%3D%3D
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="setParentNote">
       <input type="hidden" name="appcode" value="API04">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="3">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We3J3mwgjW5pdUvFK3/IZ4mJ4bMyfKTmEoup+3tTE9GeLQ==</textarea>
    </form>
  ```