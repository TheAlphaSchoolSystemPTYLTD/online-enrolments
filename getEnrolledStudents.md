**getEnrolledStudents**
----
  Returns the enrolment details for the students based on the specified parameters, or an empty "DATA" array if no matching students are found in JSON format.

* **Version History:**

    TASS v54.3 PR2 - Method Added

* **Version:**

  3

* **Permission:**

    Enrolments > Enrolments/Enrolled Student - View

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
        "RESIDENT_STS":"",
        "SUD39_BILL":"",
        "SUD1_FLG":"",
        "DISTANCE_ED":"N",
        "CURR_SCHOOL":"",
        "ACCEPT_DATE":"",
        "SUD42_BILL":"",
        "SUD26_BILL":"",
        "FOLLOWUP_FLG":"",
        "TFER_DATE":"",
        "ENTRY_YGRP":"",
        "DOB":"",
        "DOA":"",
        "BOARDER":"",
        "SUD43_BILL":"",
        "HOUSE":"",
        "token":{
            "timestamp":"{ts '2021-03-04 12:12:17'}",
            "studcode":"0010245"
        },
        "SUD38_BILL":"",
        "GIVEN_NAME":"",
        "SUD3_FLG":"",
        "MULTIPAR_FLG":"",
        "SUD11_CODE":"",
        "PREFERRED_SURNAME":"",
        "DATE_ARRIVAL":"",
        "ACCEPT_PAID":"",
        "HOLD_PAID":"",
        "SUD41_BILL":"",
        "RELIGION":"",
        "FTE":"",
        "SUD44_BILL":"",
        "MOB_PHONE":"",
        "SUD30_BILL":"",
        "SUD13_CODE":"",
        "SUD45_BILL":"",
        "SEX":"",
        "SUD19_CODE":"",
        "SUD10_FLG":"",
        "ENTRY_YGRP_DESC":"",
        "FOLLOWUP_DATE":"",
        "SUD4_FLG":"",
        "CURR_YEAR_GRP":"",
        "PREFERRED_NAME":"",
        "INTERVIEW_FLG":"",
        "SUD35_BILL":"",
        "SUD25_TEXT":"",
        "SUD8_FLG":"",
        "SUD32_BILL":"",
        "UPDATE_BY":"",
        "E_MAIL":"",
        "SUD22_TEXT":"",
        "SUD29_BILL":"",
        "CMPY_CODE":10,
        "SUD6_FLG":"",
        "INTERVIEW_DATE":"",
        "SUD20_CODE":"",
        "SUD21_TEXT":"",
        "__tassversion":"01.000.043.0",
        "MODE":"add",
        "SUD16_CODE":"",
        "FFPOS":"",
        "SUD34_BILL":"",
        "PCTUT_GRP":"",
        "SUD9_FLG":"",
        "OFFER_DATE":"",
        "SUD17_CODE":"",
        "IDM_ID":"",
        "DISPLAYNAME":"New Enrolled Student Record",
        "ASSESS_FLG":"",
        "SUD14_CODE":"",
        "CAMPUS_CODE":"",
        "SUD23_TEXT":"",
        "SUD33_BILL":"",
        "SUD36_BILL":"",
        "VISA_SUBCLASS":"",
        "OTHER_NAME":"",
        "HPAID_DATE":"",
        "SUD2_FLG":"",
        "VISA_EXPIRY":"",
        "STUD_ID":"",
        "SUD24_TEXT":"",
        "SUD5_FLG":"",
        "SUD28_BILL":"",
        "SUD37_BILL":"",
        "SUD31_BILL":"",
        "ASSESS_DATE":"",
        "FIRST_NAME":"",
        "ALT_ID":"",
        "SUD40_BILL":"",
        "SUD27_BILL":"",
        "SURNAME":"",
        "SUD7_FLG":"",
        "PRIVACY_FLG":"N",
        "PROSP_FLG":"",
        "SUD18_CODE":"",
        "PAR_CODE":"",
        "SUD15_CODE":"",
        "SMS_FLG":"",
        "STUD_CODE":"",
        "PLACE_OFFERED":"",
        "FORM_CLS":"",
        "PROSP_DATE":"",
        "LW_ADD_NUM":"",
        "ENTRY_YR":"",
        "SUD12_CODE":"",
        "UPDATE_ON":""
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
    {
        "studcode":"0010245"
    }
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
