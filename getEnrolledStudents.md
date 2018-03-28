**getEnrolledStudents**
----
  Returns the enrolment details for the students based on the specified parameters, or an empty "DATA" array if no matching students are found in JSON format.

* **Version History:**

    TASS v48.0 - Method Added

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
        "RESIDENT_STS": "",
        "SUD1_FLG": "",
        "SUD39_BILL": "",
        "CURR_SCHOOL": "",
        "ACCEPT_DATE": "",
        "SUD42_BILL": "",
        "SUD26_BILL": "",
        "FOLLOWUP_FLG": "N",
        "TFER_DATE": "",
        "ENTRY_YGRP": 7,
        "DOB": "1998-03-05 00:00:00.0",
        "DOA": "2003-08-22 00:00:00.0",
        "BOARDER": "N",
        "SUD43_BILL": "",
        "HOUSE": "",
        "SUD38_BILL": "",
        "GIVEN_NAME": "Kerry",
        "SUD3_FLG": "",
        "MULTIPAR_FLG": "N",
        "SUD11_CODE": "",
        "DATE_ARRIVAL": "",
        "ACCEPT_PAID": "N",
        "HOLD_PAID": "N",
        "SUD41_BILL": "",
        "RELIGION": "",
        "FTE": 1,
        "SUD44_BILL": "",
        "MOB_PHONE": "",
        "SUD30_BILL": "",
        "SUD13_CODE": "",
        "SUD45_BILL": "",
        "SEX": "M",
        "SUD10_FLG": "",
        "SUD19_CODE": "",
        "FOLLOWUP_DATE": "",
        "SUD4_FLG": "",
        "CURR_YEAR_GRP": "",
        "PREFERRED_NAME": "Kerry",
        "INTERVIEW_FLG": "N",
        "SUD35_BILL": "",
        "SUD25_TEXT": "",
        "SUD8_FLG": "",
        "UPDATE_BY": "ken",
        "SUD32_BILL": "",
        "E_MAIL": "",
        "SUD22_TEXT": "",
        "SUD29_BILL": "",
        "CMPY_CODE": 10,
        "SUD6_FLG": "",
        "INTERVIEW_DATE": "",
        "SUD20_CODE": "",
        "SUD21_TEXT": "",
        "MODE": "edit",
        "SUD16_CODE": "",
        "SUD34_BILL": "",
        "PCTUT_GRP": "",
        "SUD9_FLG": "",
        "OFFER_DATE": "",
        "SUD17_CODE": "",
        "DISPLAYNAME": " Kerry Albert",
        "ASSESS_FLG": "N",
        "SUD14_CODE": "",
        "CAMPUS_CODE": "",
        "SUD23_TEXT": "",
        "SUD33_BILL": "",
        "SUD36_BILL": "",
        "VISA_SUBCLASS": "",
        "HPAID_DATE": "",
        "SUD2_FLG": "",
        "VISA_EXPIRY": "",
        "STUD_ID": "487342A8-83A8-446C-88E9141491D0F9F2",
        "SUD24_TEXT": "",
        "SUD5_FLG": "",
        "SUD28_BILL": "",
        "SUD37_BILL": "",
        "SUD31_BILL": "",
        "ASSESS_DATE": "",
        "ALT_ID": "",
        "SUD40_BILL": "",
        "SUD27_BILL": "",
        "SURNAME": "Albert",
        "SUD7_FLG": "",
        "PRIVACY_FLG": "N",
        "PROSP_FLG": "Y",
        "SUD18_CODE": "",
        "PAR_CODE": 10005,
        "SMS_FLG": "N",
        "SUD15_CODE": "",
        "STUD_CODE": 20065,
        "PLACE_OFFERED": "N",
        "FORM_CLS": "",
        "PROSP_DATE": "2003-08-22 00:00:00.0",
        "LW_ADD_NUM": "",
        "ENTRY_YR": 2017,
        "UPDATE_ON": "2016-03-02 00:00:00.0",
        "SUD12_CODE": ""
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
    studcode=20065
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