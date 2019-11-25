**getEnrolledStudents**
----
  Returns the enrolment details for the students based on the specified parameters, or an empty "DATA" array if no matching students are found in JSON format.

* **Version History:**

    TASS v48.0 - Method Added

    TASS v52.0 - Return three new fields `preferred_surname`, `first_name`, `other_name` in result.

* **Version:**

  1

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**
 
   none

   **Optional:**

   none

   **Conditional:**

   `application_id [string]` - Enrolment Application ID. Invalid if `studcode` or `parcode` supplied.

   `studcode [string]` - Student Code. Invalid if `application_id` or `parcode` supplied.

   `parcode [string]` - Parent Code. Invalid if `application_id` or `studcode` supplied.

* **Success Response:** (Application has been processed)

    ```javascript
    {
        "RESIDENT_STS": "AUS",
        "SUD39_BILL": "",
        "SUD1_FLG": "Y",
        "CURR_SCHOOL": "STP",
        "ACCEPT_DATE": "2018-01-01 00:00:00.0",
        "SUD42_BILL": "",
        "SUD26_BILL": "",
        "FOLLOWUP_FLG": "Y",
        "TFER_DATE": "2019-03-20 00:00:00.0",
        "ENTRY_YGRP": 7,
        "DOB": "1995-10-14 00:00:00.0",
        "DOA": "2018-01-01 00:00:00.0",
        "BOARDER": "Y",
        "SUD43_BILL": "",
        "HOUSE": "AC",
        "token": {
            "timestamp": "{ts '2019-11-05 09:04:38'}",
            "studcode": "0010245"
        },
        "SUD38_BILL": "",
        "GIVEN_NAME": "Ian Peter",
        "SUD3_FLG": "Y",
        "MULTIPAR_FLG": "Y",
        "SUD11_CODE": "ARG",
        "PREFERRED_SURNAME": "Aardvaark",
        "DATE_ARRIVAL": "2013-10-03 00:00:00.0",
        "ACCEPT_PAID": "Y",
        "HOLD_PAID": "W",
        "SUD41_BILL": "",
        "RELIGION": "RC",
        "FTE": 1,
        "SUD44_BILL": "",
        "MOB_PHONE": "0412016500",
        "SUD30_BILL": "",
        "SUD13_CODE": "AU",
        "SUD45_BILL": "",
        "SEX": "M",
        "__locks": {},
        "SUD19_CODE": "OK",
        "SUD10_FLG": "",
        "ENTRY_YGRP_DESC": 7,
        "FOLLOWUP_DATE": "2018-01-01 00:00:00.0",
        "SUD4_FLG": "N",
        "CURR_YEAR_GRP": 4,
        "PREFERRED_NAME": "Fred",
        "INTERVIEW_FLG": "Y",
        "SUD35_BILL": "",
        "SUD25_TEXT": 40,
        "SUD8_FLG": "N",
        "SUD32_BILL": "",
        "UPDATE_BY": "ken",
        "__invalid": {},
        "E_MAIL": "iAardvaark@tassweb.com.au",
        "SUD22_TEXT": "2/02/2018",
        "SUD29_BILL": "",
        "CMPY_CODE": 10,
        "SUD6_FLG": "N",
        "INTERVIEW_DATE": "2018-01-01 00:00:00.0",
        "SUD20_CODE": "ABC",
        "SUD21_TEXT": 21,
        "MODE": "edit",
        "SUD16_CODE": "CP",
        "SUD34_BILL": "",
        "PCTUT_GRP": "7STAR",
        "SUD9_FLG": "Y",
        "OFFER_DATE": "2018-01-01 00:00:00.0",
        "SUD17_CODE": "SML",
        "IDM_ID": "",
        "DISPLAYNAME": " Ian Peter Aardvaark",
        "ASSESS_FLG": "Y",
        "SUD14_CODE": "TE",
        "CAMPUS_CODE": "SE",
        "SUD23_TEXT": 8,
        "__status": "success",
        "SUD33_BILL": "",
        "SUD36_BILL": "",
        "VISA_SUBCLASS": "XX",
        "OTHER_NAME": "Peter",
        "HPAID_DATE": "2018-01-01 00:00:00.0",
        "SUD2_FLG": "N",
        "VISA_EXPIRY": "2015-12-31 00:00:00.0",
        "STUD_ID": "87F114E4-587C-4407-9568DD413E5FD0FE",
        "SUD24_TEXT": 9,
        "SUD5_FLG": "Y",
        "SUD28_BILL": "",
        "SUD37_BILL": "",
        "SUD31_BILL": "",
        "ASSESS_DATE": "2018-01-01 00:00:00.0",
        "FIRST_NAME": "Ian",
        "ALT_ID": "AARDY",
        "SUD40_BILL": "",
        "SUD27_BILL": "",
        "SURNAME": "Aardvaark",
        "SUD7_FLG": "Y",
        "PRIVACY_FLG": "Y",
        "PROSP_FLG": "Y",
        "SUD18_CODE": 61,
        "PAR_CODE": "000916",
        "SUD15_CODE": "EXA",
        "SMS_FLG": "Y",
        "STUD_CODE": "0010245",
        "PLACE_OFFERED": "Y",
        "FORM_CLS": "C",
        "PROSP_DATE": "2018-01-01 00:00:00.0",
        "LW_ADD_NUM": "",
        "ENTRY_YR": 2019,
        "SUD12_CODE": "AUS",
        "UPDATE_ON": "2019-03-20 00:00:00.0"
    }
    ```
* **Success Response:** (Application has NOT been processed)

    ```javascript
      {
        "application_id": "APPLICATION123",
        "status": "Submitted"
      }
    ```
    
* **Error Response:**

    `studcode` and `parcode` and `application_id` are exclusive
    ```javascript
      "__msg":"'studcode' AND 'parcode' AND 'application_id' ARE EXCLUSIVE"
    ```
    
    `studcode` or `parcode` or `application_id` are required
    ```javascript
      "__msg":"'studcode' OR 'parcode' OR 'application_id' REQUIRED"
    ```
    
* **Sample Parameters:**

  ```javascript
    studcode=0010245
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
    http://api.tasscloud.com.au/tassweb/api/?method=GetEnrolledStudents&appcode=DEMOOE&company=10&token=7pc7yVecfoW7ly9LjqB3Ow%3D%3D
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
      <input type="hidden" name="method" value="getEnrolledStudents" />
      <input type="hidden" name="appcode" value="DEMOOE" />
      <input type="hidden" name="company" value="10" />
      <textarea name="token">7pc7yVecfoW7ly9LjqB3Ow==</textarea>
    </form>
  ```
