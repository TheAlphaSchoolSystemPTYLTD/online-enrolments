**setStudentMedicalConditions**
----
  Returns "success" and a count of updated and/or failed student medical conditions record(s), or a structure of invalid validations messages belonging to student medical conditions record(s).
  
* **Version History:**

  TASS v57.8.100 - Method Added

* **Version:**

  3

* **Permission:**

  Medical Records > Student Medical > Medical Conditions > Edit

* **Method:**

  `GET | POST`
  
* **Params:**

  **Required:**
 
  `stud_code [string]` - Student Code

  `mcond_code [string]` - Medical Condition Code

  **Optional:**

  *NOTE:* If use empty string, the original value will be cleared for optional fields.

  `last_occ_date [date]` - Date of Last Occurence (Date Format: yyyy-mm-dd)

  `treat_text [string]` - General Note (length limit 4000)

  `smcud1-10_text [string]` - Accident Other Details (UD) 1 - 10 fields (length limit 200)

  `attachments [array]` - include one or multiple Medical Attachment item(s)

  `requirements [array]` - include one or multiple Medical Requirement item(s)

  `notes [array]` - include one or multiple Medical Note item(s)

  **Conditional:**

  For item(s) in the attachments array:

  `attachment_file [string]` - field is required where 'attachment_file_name' is supplied for each item in 'attachments'. (URLEncoded Format is RECOMMENDED)

  `attachment_file_name [string]` - field is required where 'attachment_file' is supplied for each item in 'attachments'.

  For item(s) in the requirements array:

  `med_text [string]` - field is required for each item in 'requirements' if adding a new record. Optional if editing an existing record.

  `med_num[string]` - field is optional for each item in 'requirements'. If the provided med_num exists, the program will try to update a record accordingly.

  `med_meth [string]` - field is optional for each item in 'requirements'.

  `med_detl [string]` - field is optional for each item in 'requirements'.

  `note_date [date]` - field is optional for each item in 'notes', (Date Format: yyyy-mm-dd).

  `note_text [string]` - field is optional for each item in 'notes'.

* **Success Response:**

  ```javascript
  {
    "success":"You successfully saved Enrolled Student Medical Data.",
    "__tassversion":"01.054.4.000",
    "token":{
      "treat_text":"test note here",
      "requirements":[
        {
          "MED_DETL":"",
          "med_text":"bananas N cheese XD",
          "med_num":1,
          "MED_METH":"tablets"
        },
        {
          "med_detl":"unknown",
          "med_text":"new med",
          "med_num":"",
          "med_meth":"new method"
        },
        {
          "med_detl":"details",
          "med_text":"new two",
          "MED_NUM":"",
          "MED_METH":""
        }
      ],
      "notes":[
        {
          "note_date":"2022-06-23",
          "note_text":"This is a note for testing"
        }
      ],
      "smcud1_text":"12345678901234567890",
      "stud_code":"0009130",
      "last_occ_date":"16/06/2022",
      "attachments":[
        {
          "attachment_file_name":"test",
          "attachment_file":"ClRoaXMgaXMgYSB0ZXN0IGZpbGUuCkRvIG5vdCBpbmNsdWRlIGEgdGFibGUhISEKTmFtZQlRdWFudGl0eQlWYWx1ZQppUGFkCTEJNTAwCmlQaG9uZQkxCTEwMDAKVG90YWwJMgkxNTAw"
        }
      ],
      "timestamp":"{ts '2022-06-24 11:18:18'}",
      "mcond_code":"ACC"
    }
  }
  ```

* **Error Response:**

  `stud_code` not supplied
  ```javascript
  __invalid: {
    "__msg": "stud_code' is required."
  }
  ```

  `mcond_code` not supplied
  ```javascript
  __invalid: {
    "__msg": "mcond_code' is required."
  }
  ```

  `last_occ_date` not supplied
  ```javascript
  __invalid: {
    "__msg": "'last_occ_date' date format is invalid."
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

  For each item in 'attachments': attachment_file is passed in but attachment_file_name is not passed in
  ```javascript
  __invalid: {
    "attachment_file_name": "attachment_file_name field is required where 'attachment_file' is supplied."
  }
  ```

  For each item in 'attachments': attachment_file_name is passed in but attachment_file is not passed in
  ```javascript
  __invalid: {
    "attachment_file": "attachment_file field is required where 'attachment_file_name' is supplied."
  }
  ```

  For each item in 'attachments': attachment_file_name exceeds 255 characters
  ```javascript
  __invalid: {
    "attachment_file_name": "attachment_file_name must be between 1 and 255 characters."
  }
  ```

  med_text is required when adding new medical requirements
  ```javascript
  __invalid: {
    "med_text": "med_text' IS REQUIRED in 'requirements' item."
  }
  ```

  med_num is required when adding new medical requirements
  ```javascript
  __invalid: {
    "med_num": "med_num' IS REQUIRED in 'requirements' item."
  }
  ```

  note_date is required when adding/editing medical notes
  ```javascript
  __invalid: {
    "note_date": "note_date' IS REQUIRED."
  }
  ```

  note is required when adding/editing medical notes
  ```javascript
  __invalid: {
    "note": "note' IS REQUIRED."
  }
  ```
    
* **Sample Parameters:**

  ```javascript
  {
    "stud_code":"0009130",
    "mcond_code":"ACC",
    "last_occ_date":"16/06/2022",
    "treat_text":"test note here",
    "smcud1_text":"12345678901234567890",
    "attachments":[
      {
        "attachment_file_name":"test",
        "attachment_file":"ClRoaXMgaXMgYSB0ZXN0IGZpbGUuCkRvIG5vdCBpbmNsdWRlIGEgdGFibGUhISEKTmFtZQlRdWFudGl0eQlWYWx1ZQppUGFkCTEJNTAwCmlQaG9uZQkxCTEwMDAKVG90YWwJMgkxNTAw"
      }
    ],
    "requirements":[
      {
        "med_num":"1",
        "med_text":"bananas N cheese XD"
      },
      {
        "med_num":"",
        "med_text":"new med",
        "med_meth":"new method",
        "med_detl":"unknown"
      },
      {
        "med_text":"new two",
        "med_detl":"details"
      }
    ],
    "notes":[
      {
        "note_date":"23/06/2022",
        "note_text":"This is a note for testing"
      }
    ]
  }
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
    http://api.tasscloud.com.au/tassweb/api/?method=setStudentMedicalConditions&appcode=API04&company=10&v=3&token=l1D8owEn111IHcXLRwXTB0oU2GX6rj%2BISqa9zXA8We3J3mwgjW5pdUvFK3%2FIZ4mJ4bMyfKTmEoup%2B3tTE9GeLQ%3D%3D
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="setStudentMedicalConditions">
       <input type="hidden" name="appcode" value="API04">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="3">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We3J3mwgjW5pdUvFK3/IZ4mJ4bMyfKTmEoup+3tTE9GeLQ==</textarea>
    </form>
  ```