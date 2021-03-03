**setEnrolment**
----
  Returns "Success" if enrolment record successfully inserted, or returns "Invalid" and an array of validation "Errors" if the record is unable to be inserted .

* **Version History:**

    TASS v55.0 - Method Added

* **Version:**

  3

* **Method:**

  `GET | POST`
  
* **Params:**

    **Required:**

    `application_id [string]` - Enrolment Application ID - Length must be between 1 and 50 Characters

    `stud_surname [string]` - Student Surname - Length must be between 1 and 50 Characters

    `given_name [string]` - Student Given Name(s) - Length must be between 1 and 101 Characters

    `preferred_name [string]` - Student Preferred Name - Length must be between 1 and 50 Characters

    `dob [date dd/mm/yyyy]` - Student Date of Birth

    `sex [string]` - Student Gender - Length must be between 1 and 3 Characters

    `entry_yr [integer]` - Year of Student Entry

    `entry_ygrp [integer]` - Student Year Group when Starting

    `boarder [string]` - Is the Student a Boarder - Length must be 1 Character(Y/N) 

    `doa [date dd/mm/yyyy]` - Date of Enrolment Application

    `par_surname [string]` - Parent Surname - Length must be between 1 and 30 Characters

    `par_name [string]` - Parent Full Name - Length must be between 1 and 61 Characters

    **Optional:**

    `religion [string]` - Student Religion - Length must be between 1 and 2 Characters

    `curr_year_grp [integer]` - Current Year Group

    `curr_school [string]` - Current School - Length must be between 1 and 5 Characters

    `prosp_flg [string]` - Stage 1 Flag - Length must be 1 Character(Y/N)

    `prosp_date [date dd/mm/yyyy]` - Stage 1 Date

    `followup_flg [string]` - Stage 2 Flag - Length must be 1 Character(Y/N)

    `followup_date [date dd/mm/yyyy]` - Stage 2 Date

    `hold_paid [string]` - Stage 3 Flag - Length must be 1 Character(Y/N)

    `hpaid_date [date dd/mm/yyyy]` - Stage 3 Date

    `interview_flg [string]` - Stage 4 Flag - Length must be 1 Character(Y/N)

    `interview_date [date dd/mm/yyyy]` - Stage 4 Date

    `assess_flg [string]` - Stage 5 Flag - Length must be 1 Character(Y/N)

    `assess_date [date dd/mm/yyyy]` - Stage 5 Date

    `place_offered [string]` - Stage 6 Flag - Length must be 1 Character(Y/N)

    `offer_date [date dd/mm/yyyy]` - Stage 6 Date

    `accept_paid [string]` - Stage 7 Flag - Length must be 1 Character(Y/N)

    `accept_date [date dd/mm/yyyy]` - Stage 7 Date

    `e_mail [string]` - Student Email - Length must be between 1 and 60 Characters

    `campus_code [string]` - Student Campus - Length must be between 1 and 3 Characters

    `mob_phone [string]` - Student Mobile Phone - Length must be between 1 and 30 Characters

    `resident_sts [string]` - Student Residency Status - Length must be between 1 and 3 Characters

    `visa_expiry [date dd/mm/yyyy]` - Student Visa Expiry

    `visa_subclass [string]` - Student Visa Subclass - Length must be between 1 and 6 Characters

    `date_arrival [date dd/mm/yyyy]` - Student Date Arrival in Aus

    `s_indig_sts [string]` - MCEECDYA Student Indigenous Status - Length must be 1 Character

    `mse_code [string]` - MCEECDYA Mother School Education - Length must be 1 Character

    `fse_code [string]` - MCEECDYA Father School Education - Length must be 1 Character

    `mnse_code [string]` - MCEECDYA Mother Non-School Education - Length must be 1 Character

    `fnse_code [string]` - MCEECDYA Father Non-School Education - Length must be 1 Character

    `mocc_code [string]` - MCEECDYA Mother Occupation Group - Length must be 1 Character

    `focc_code [string]` - MCEECDYA Father Occupation Group - Length must be 1 Character

    `slote_code [string]` - MCEECDYA Student Language other than English Code - Length must be between 1 and 4 Characters

    `mlote_code [string]` - MCEECDYA Mother Language other than English Code - Length must be between 1 and 4 Characters

    `flote_code [string]` - MCEECDYA Father Language other than English Code - Length must be between 1 and 4 Characters

    `scob_code [string]` - MCEECDYA Student Country of Birth - Length must be between 1 and 4 Characters

    `arrive_yr [string]` - Student year of arrival in Australia - Length must be between 1 and 4 Characters

    `sud1_flg to sud10_flg [string]` - Student user defined flag - Length must be 1 Character

    `sud11_code to sud20_code [string]` - Student user defined code - Length must be between 1 and 3 Characters

    `sud21_text to sud25_text [string]` - Student user defined text - Length must be between 1 and 20 Characters

    `prev_conn [string]` - Previous connections - Length must be between 1 and 2 Characters

    `pud1_flg to pud10_flg [string]` - Parent user defined flag - Length must be 1 Character

    `pud11_code to pud20_code [string]` - Parent user defined code - Length must be between 1 and 3 Characters

    `pud21_text to pud25_text [string]` - Parent user defined text - Length must be between 1 and 20 Characters

    `f_occ [string]` - Father occupation code - Length must be between 1 and 3 Characters(values will be truncated)

    `m_occ [string]` - Mother occupation code - Length must be between 1 and 3 Characters(values will be truncated)

    `par_name2 [string]` - Parent name 2 - Length must be between 1 and 30 Characters

    `addr1 [string]` - Address 1 - Length must be between 1 and 50 Characters

    `addr2 [string]` - Address 2 - Length must be between 1 and 50 Characters

    `addr3 [string]` - Address 3 - Length must be between 1 and 50 Characters

    `town_sub [string]` - Town suburb - Length must be between 1 and 30 Characters

    `state_code [string]` - State code - Length must be between 1 and 3 Characters

    `post_code [string]` - Post code - Length must be between 1 and 10 Characters

    `country [string]` - Country - Length must be between 1 and 20 Characters

    `dpid_text [string]` - Address Barcode (DPID Barcode) - Length must be between 1 and 40 Characters

    `home_phone [string]` - Home phone - Length must be between 1 and 30 Characters

    `bus_phone [string]` - Business phone - Length must be between 1 and 30 Characters

    `fax [string]` - Fax - Length must be between 1 and 30 Characters

    `salutation [string]` - Salutation - Length must be between 1 and 60 Characters

    `par_e_mail [string]` - Parent email - Length must be between 1 and 140 Characters

    `par_e_mail2 [string]` - Parent email2 - Length must be between 1 and 140 Characters

    `mobile1 [string]` - Mobile 1 - Length must be between 1 and 30 Characters

    `sms_flg1 [string]` - SMS flag 1 - Length must be 1 Character(Y/N)

    `mobile2 [string]` - Mobile 2 - Length must be between 1 and 30 Characters

    `sms_flg2 [string]` - SMS flag 2 - Length must be 1 Character(Y/N)

    `rec_type [string]` - Receipt Type - Length must be 1 Character \ 
    D = Deposit (Refundable)  \
    A = Advance (Fees Prepayment)  \
    G = General (Revenue Recognised)  \
    E = Enrolment Fee (Revenue Deferred)

    `rec_date [date dd/mm/yyyy]` - Receipt Date

    `web_cash_num [integer]` - Online Receipt Reference Number

    `cash_amt [decimal (16,2)]` - Receipt Amount

    `batch_num [integer]` - Batch Number  \
    Where populated, it will be a 9 digit numeric string based on the Settlement Date (yyyymmdd) prefixed with a “6”

    `stud_first_name [string]` - Student First Name - Length must be between 1 and 50 Characters

    `stud_other_names [string]` - Student Other Names - Length must be between 1 and 50 Characters

    `stud_preferred_surname [string]` - Student Preferred Surname (use stud_surname if not supplied) - Length must be between 1 and 50 Characters

    **Conditional:**

    `f_name [string]` - Father name (invalid when name tokens supplied, required when not supplied. Format: "Title FirstName Other Names Surname")

    `m_name [string]` - Mother name (invalid when name tokens supplied, required when not supplied. Format: "Title FirstName Other Names Surname")

    `Name Tokens`:

    `f_title [string]` - Father Title - Length must be between 1 and 10 Characters

    `f_initials [string]` - Father Initials - Length must be between 1 and 5 Characters

    `f_surname [string]` - Father Surname - Length must be between 1 and 50 Characters

    `f_first_name [string]` - Father First Name - Length must be between 1 and 50 Characters

    `f_other_names [string]` - Father Other Names - Length must be between 1 and 50 Characters

    `f_preferred_name [string]` - Father Preferred Name - Length must be between 1 and 50 Characters

    `f_suffix [string]` - Father Suffix - Length must be between 1 and 50 Characters

    `m_title [string]` - Mother Title - Length must be between 1 and 10 Characters

    `m_initials [string]` - Mother Initials - Length must be between 1 and 5 Characters

    `m_surname [string]` - Mother Surname - Length must be between 1 and 50 Characters

    `m_first_name [string]` - Mother First Name - Length must be between 1 and 50 Characters

    `m_other_names [string]` - Mother Other Names - Length must be between 1 and 50 Characters

    `m_preferred_name [string]` - Mother Preferred Name - Length must be between 1 and 50 Characters

    `m_suffix [string]` - Mother Suffix - Length must be between 1 and 50 Characters

    `m_p1_sex [string]` - Mother / Parent 1 [strPositionLabels.motherLabel] Gender - Length must be between 1 and 3 Characters

    `f_p2_sex [string]` - Father / Parent 2 [strPositionLabels.fatherLabel] Gender - Length must be between 1 and 3 Characters

* **Success Response:**

    ```javascript
    {
        "__status": "success",
        "errors": [],
        "__tassversion": "01.053.3.000",
        "__invalid": {},
        "__locks": {},
        "token": {
                "given_name": "Posy",
                "sex": "F",
                "application_id": 20211901,
                "par_surname": "Renowa",
                "stud_surname": "Renowa",
                "f_p2_sex": "M",
                "entry_ygrp": 1,
                "batch_num": 612345678,
                "preferred_name": "Posy",
                "dob": "2000-01-01",
                "par_name": "Hugh & Rachel",
                "f_name": "Hugh Renowa",
                "boarder": "N",
                "doa": "2019-09-29",
                "m_p1_sex": "F",
                "timestamp": "{ts '2021-01-19 15:00:29'}",
                "m_name": "Rachel Clearland",
                "entry_yr": 2021
        }
    }
    ```
 
* **Error Response:**

    Required `[field_name]` not supplied
    ```javascript
      "__msg": "[field_name] must be specified."
    ```

    Date `[field_name]` not a valid date
    ```javascript
      "__msg": "[field_name] is invalid."
    ```
    
    Integer `[field_name]` not a valid integer
    ```javascript
      "__msg": "[field_name] is invalid."
    ```

    Decimal `[field_name]` not a valid decimal
    ```javascript
      "__msg": "[field_name] is invalid."
    ```

    `application_id` already exist (Only if the Application has already been processed. Otherwise this new Applciation will replace the previous unprocessed Application)
    ```javascript
      "__msg": "Application ID 'application_id' is not unique."
    ```

    `application_id` exceed 50 characters
    ```javascript
      "__msg": "Application ID 'application_id' exceeded 50 characters."
    ```

    `sex` not defined in genders setup
    ```javascript
      "__msg": "Student Gender is invalid."
    ```

    `boarder` not 'Y' or 'N'
    ```javascript
      "__msg": "Boarder is invalid."
    ```

    `rec_type` not 'D' or 'G' or 'A' or 'D'
    ```javascript
      "__msg": "Receipt Type is invalid."
    ```

    `cash_amt` must be 0.00 or a positive number with 2 decimal points
    ```javascript
      "__msg": "Receipt Amount is invalid."
    ```

    `e_mail` length longer than 60
    ```javascript
      "__msg": "e_mail cannot be longer than 60 characters."
    ```

    `e_mail` must be a valid Email
    ```javascript
      "__msg": "e_mail is invalid."
    ```

    `par_e_mail` length longer than 60
    ```javascript
      "__msg": "par_e_mail cannot be longer than 60 characters."
    ```

    `par_e_mail` must be a valid Email
    ```javascript
      "__msg": "par_e_mail is invalid."
    ```

    `par_e_mail2` length longer than 60
    ```javascript
      "__msg": "par_e_mail2 cannot be longer than 60 characters."
    ```

    `par_e_mail2` must be a valid Email
    ```javascript
      "__msg": "par_e_mail2 is invalid."
    ```
    
    `m_name` & `f_name` and `Name Tokens` not supplied
    ```javascript
      "__msg": "m_name/f_name required when name tokens not supplied."
    ```

    `m_name` and `Name Tokens` both supplied
    ```javascript
      "__msg": "m_name invalid when name tokens supplied."
    ```

    `f_name` and `Name Tokens` both supplied
    ```javascript
      "__msg": "f_name invalid when name tokens supplied."
    ```

    `m_name` & `f_name` and `Name Tokens` both supplied
    ```javascript
      "__msg": "m_name/f_name invalid when name tokens supplied."
    ```

    `m_name` supplied but has only one word
    ```javascript
      "__msg": "m_name must contain at least two name tokens (first_name & surname)."
    ```

    `f_name` supplied but has only one word
    ```javascript
      "__msg": "f_name must contain at least two name tokens (first_name & surname)."
    ```

    `m_p1_sex` not defined in genders setup
    ```javascript
      "__msg": "[strPositionLabels.motherLabel] Gender is invalid."
    ```

    `f_p2_sex` not defined in genders setup
    ```javascript
      "__msg": "[strPositionLabels.fatherLabel] Gender is invalid."
    ```

    `m_p1_sex` supplied but `m_name` or mother name tokens is/are not supplied
    ```javascript
      "__msg": "[strPositionLabels.motherLabel] Gender must be empty string."
    ```

    `f_p2_sex` supplied but `f_name` or father name tokens is/are not supplied
    ```javascript
      "__msg": "[strPositionLabels.fatherLabel] Gender must be empty string."
    ```

* **Sample Parameters:**

  ```javascript
    {
        "application_id": "ANTONY05",
        "stud_surname": "Anton",
        "given_name": "Edward",
        "preferred_name": "Pie",
        "dob": "2000-01-01",
        "sex": "M",
        "entry_yr": "2020",
        "entry_ygrp": 11,
        "boarder": "N",
        "doa": "2019-09-29",
        "par_surname": "Austin",
        "par_name": "John %26 Mary",
        "m_name": "Mrs Mary Mid Austin",
        "f_name": "Mr John Fid Austin",
        "m_p1_sex": "F",
        "f_p2_sex": "M",
        "batch_num": "612345678"
    }
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
    http://api.tasscloud.com.au/tassweb/api/?method=SetEnrolment&appcode=DEMOOE&company=10&token=wJ4E9t7kNMFLndpo50f8UyZNl1aPs4Mlr6KvJPDBvshdD2CuTIZUFFqBBkPxxistvyHOze8yP6cJ5euVnnk1Of%2Bw4h9HWjsgcra8BcAfEi6HNq8eo7bmb%2BAb%2B7toUIIFiMOlf69Xy8R4yb5349VPGZs1BUw5SpSHuX84PP6s1aYyanzDNslZxCk7zRFgK1n894HZR3Dkh8lMRdQyQMaVunS66Iwuj8g0ElU9FhTTlOoInzSo0e9L1P8s5ooQZ6XUlRrMx1%2BoZ4ZUe1lYdof1LA%3D%3D
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="setEnrolment">
       <input type="hidden" name="appcode" value="DEMOAP">
       <input type="hidden" name="company" value="10">
       <textarea name="token">wJ4E9t7kNMFLndpo50f8UyZNl1aPs4Mlr6KvJPDBvshdD2CuTIZUFFqBBkPxxistvyHOze8yP6cJ5euVnnk1Of+w4h9HWjsgcra8BcAfEi6HNq8eo7bmb+Ab+7toUIIFiMOlf69Xy8R4yb5349VPGZs1BUw5SpSHuX84PP6s1aYyanzDNslZxCk7zRFgK1n894HZR3Dkh8lMRdQyQMaVunS66Iwuj8g0ElU9FhTTlOoInzSo0e9L1P8s5ooQZ6XUlRrMx1+oZ4ZUe1lYdof1LA==</textarea>
    </form>
  ```
