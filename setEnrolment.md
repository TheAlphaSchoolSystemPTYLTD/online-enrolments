**setEnrolment**
----
  Returns "Success" if enrolment record successfully inserted, or returns "Invalid" and an array of validation "Errors" if the record is unable to be inserted .

* **Version History:**

    TASS v48.0 - Method Added

    TASS v51.4 - Added a new field par_e_mail2. Added validation for e_mail, par_e_mail, and par_e_mail2.

    TASS v52.0 - Add 17 new fields `stud_first_name`, `stud_other_names`, `stud_preferred_surname`, `f_title`, `f_initials`, `f_surname`, `f_first_name`, `f_other_names`, `f_preferred_name`, `f_suffix`, `m_title`, `m_initials`, `m_surname`, `m_first_name`, `m_other_names`, `m_preferred_name`, `m_suffix`. User needs to either supply parents' name tokens or `m_name` & `f_name`.

* **Version:**

  1

* **Method:**

  `GET | POST`
  
* **Params:**

    **Required:**

    `application_id [string]` - Enrolment Application ID

    `stud_surname [string]` - Student Surname

    `given_name [string]` - Student Given Name(s)

    `preferred_name [string]` - Student Preferred Name

    `dob [date dd/mm/yyyy]` - Student Date of Birth

    `sex [string]` - Student Gender ("M" or "F")

    `entry_yr [integer]` - Year of Student Entry

    `entry_ygrp [integer]` - Student Year Group when Starting

    `boarder [string]` - Is the Student a Boarder ("Y" or "N")

    `doa [date dd/mm/yyyy]` - Date of Enrolment Application

    `par_surname [string]` - Parent Surname

    `par_name [string]` - Parent Full Name

    **Optional:**

    `religion [string]` - Student Religion

    `curr_year_grp [integer]` - Current Year Group

    `curr_school [string]` - Current School

    `prosp_flg [string]` - Stage 1 Flag

    `prosp_date [date dd/mm/yyyy]` - Stage 1 Date

    `followup_flg [string]` - Stage 2 Flag

    `followup_date [date dd/mm/yyyy]` - Stage 2 Date

    `hold_paid [string]` - Stage 3 Flag

    `hpaid_date [date dd/mm/yyyy]` - Stage 3 Date

    `interview_flg [string]` - Stage 4 Flag

    `interview_date [date dd/mm/yyyy]` - Stage 4 Date

    `assess_flg [string]` - Stage 5 Flag

    `assess_date [date dd/mm/yyyy]` - Stage 5 Date

    `place_offered [string]` - Stage 6 Flag

    `offer_date [date dd/mm/yyyy]` - Stage 6 Date

    `accept_paid [string]` - Stage 7 Flag

    `accept_date [date dd/mm/yyyy]` - Stage 7 Date

    `e_mail [string]` - Student Email

    `campus_code [string]` - Student Campus

    `mob_phone [string]` - Student Mobile Phone

    `resident_sts [string]` - Student Residency Status

    `visa_expiry [date dd/mm/yyyy]` - Student Visa Expiry

    `visa_subclass [string]` - Student Visa Subclass

    `date_arrival [date dd/mm/yyyy]` - Student Date Arrival in Aus

    `s_indig_sts [string]` - MCEECDYA Student Indigenous Status

    `mse_code [string]` - MCEECDYA Mother School Education

    `fse_code [string]` - MCEECDYA Father School Education

    `mnse_code [string]` - MCEECDYA Mother Non-School Education

    `fnse_code [string]` - MCEECDYA Father Non-School Education

    `mocc_code [string]` - MCEECDYA Mother Occupation Group

    `focc_code [string]` - MCEECDYA Father Occupation Group

    `slote_code [string]` - MCEECDYA Student Language other than English Code

    `mlote_code [string]` - MCEECDYA Mother Language other than English Code

    `flote_code [string]` - MCEECDYA Father Language other than English Code

    `scob_code [string]` - MCEECDYA Student Country of Birth

    `arrive_yr [string]` - Student year of arrival in Australia.

    `sud1_flg to sud10_flg [string]` - Student user defined flag

    `sud11_code to sud20_code [string]` - Student user defined code

    `sud21_text to sud25_text [string]` - Student user defined text

    `prev_conn [string]` - Previous connections

    `pud1_flg to pud10_flg [string]` - Parent user defined flag

    `pud11_code to pud20_code [string]` - Parent user defined code

    `pud21_text to pud25_text [string]` - Parent user defined text

    `f_occ [string]` - Father occupation code. Max 3 characters (values will be truncated)

    `m_occ [string]` - Mother occupation code. Max 3 characters (values will be truncated)

    `par_name2 [string]` - Parent name 2

    `addr1 [string]` - Address 1

    `addr2 [string]` - Address 2

    `addr3 [string]` - Address 3

    `town_sub [string]` - Town suburb 

    `state_code [string]` - State code

    `post_code [string]` - Post code

    `country [string]` - Country

    `dpid_text [string]` - Address Barcode (DPID Barcode)

    `home_phone [string]` - Home phone

    `bus_phone [string]` - Business phone

    `fax [string]` - Fax

    `salutation [string]` - Salutation

    `par_e_mail [string]` - Parent email

    `par_e_mail2 [string]` - Parent email2

    `mobile1 [string]` - Mobile 1

    `sms_flg1 [string]` - SMS flag 1

    `mobile2 [string]` - Mobile 2

    `sms_flg2 [string]` - SMS flag 2

    `rec_type [string]` - Receipt Type  \
    D = Deposit (Refundable)  \
    A = Advance (Fees Prepayment)  \
    G = General (Revenue Recognised)  \
    E = Enrolment Fee (Revenue Deferred)

    `rec_date [date dd/mm/yyyy]` - Receipt Date

    `web_cash_num [integer]` - Online Receipt Reference Number

    `cash_amt [decimal]` - Receipt Amount

    `batch_num [integer]` - Batch Number  \
    Where populated, it will be a 9 digit numeric string based on the Settlement Date (yyyymmdd) prefixed with a “6”

    `stud_first_name [string]` - Student First Name

    `stud_other_names [string]` - Student Other Names

    `stud_preferred_surname [string]` - Student Preferred Surname (use stud_surname if not supplied)

    **Conditional:**

    `f_name [string]` - Father name (invalid when name tokens supplied, required when not supplied. Format: "Title FirstName Other Names Surname")

    `m_name [string]` - Mother name (invalid when name tokens supplied, required when not supplied. Format: "Title FirstName Other Names Surname")

    `Name Tokens`:

    `f_title [string]` - Father Title

    `f_initials [string]` - Father Initials

    `f_surname [string]` - Father Surname

    `f_first_name [string]` - Father First Name

    `f_other_names [string]` - Father Other Names

    `f_preferred_name [string]` - Father Preferred Name

    `f_suffix [string]` - Father Suffix

    `m_title [string]` - Mother Title

    `m_initials [string]` - Mother Initials

    `m_surname [string]` - Mother Surname

    `m_first_name [string]` - Mother First Name

    `m_other_names [string]` - Mother Other Names

    `m_preferred_name [string]` - Mother Preferred Name

    `m_suffix [string]` - Mother Suffix

* **Success Response:**

    ```javascript
    {
        "__status": "success",
        "token": {
            "given_name": "Edward",
            "sex": "M",
            "application_id": "ANTONY05",
            "par_surname": "Austin",
            "stud_surname": "Anton",
            "entry_ygrp": 11,
            "preferred_name": "Pie",
            "dob": "2000-01-01",
            "par_name": "John & Mary",
            "f_name": "Mr John Fid Austin",
            "boarder": "N",
            "doa": "2019-09-29",
            "timestamp": "{ts '2019-11-27 09:49:11'}",
            "m_name": "Mrs Mary Mid Austin",
            "entry_yr": 2019
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

    `sex` not 'M' or 'F'
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

* **Sample Parameters:**

  ```javascript
    application_id=ANTONY05&stud_surname=Anton&given_name=Edward&preferred_name=Pie&dob=2000-01-01&sex=M&entry_yr=2019&entry_ygrp=11&boarder=N&doa=2019-09-29&par_surname=Austin&par_name=John %26 Mary&m_name=Mrs Mary Mid Austin&f_name=Mr John Fid Austin
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
