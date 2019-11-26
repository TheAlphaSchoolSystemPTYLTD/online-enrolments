**getStudents**
----
  Returns an array of structured student data in JSON format.

* **Version History:**

    TASS v48.0 - Method Added

    TASS v51.4 - Return a new field par_e_mail2 as email2 in contacts.

    TASS v52.0 - Return three new fields `preferred_surname`, `first_name`, `other_name` for each student. Return 7 new fields `title`, `initials`, `surname`, `first_name`, `other_name`, `preferred_name`, `suffix` for parent1 & parent2 per contact.

* **Version:**

  1

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**
 
   `commtype [string]` - Communication Rule Type. Must be one of:
    ```HTML
        ALL - Communication Types
        ACA – Academic Reports
        ATT – Attendance
        EC – Emergency Contact
        GEN – TASS.web Correspondence
        LW – Student Lives With
        TK – Teacher Kiosk View
        TKCO – Teacher Kiosk Correspondence
    ```                       

   **Optional:**

   `studcode [string]` - Student Code for retrieving a specified single student record

   **Conditional:**

   none

* **Success Response:**

    ```javascript
    {
        "__status": "success",
        "students": [
            {
                "language": "Croatian",
                "nationality": "Turkey",
                "contacts": [
                    {
                        "mobile2": "0412016500",
                        "town_suburb": "ALBION",
                        "parent1": {
                            "initials": "P",
                            "suffix": "suf",
                            "surname": "Clark",
                            "description": "Mother/Parent 1",
                            "preferred_name": "Paula",
                            "other_name": "PauOth",
                            "title": "Mrs",
                            "first_name": "Paula"
                            },
                        "parent_name2": "",
                        "parent2": {
                            "initials": "E",
                            "suffix": "",
                            "surname": "Clark",
                            "description": "Father/Parent 2",
                            "preferred_name": "Edward",
                            "other_name": "",
                            "title": "",
                            "first_name": "Edward"
                        },
                        "email": "t.sloman84@gmail.com",
                        "mother_name": "Paula Clark",
                        "country": "AUSTRALIA",
                        "salutation": "Mr and Mrs Clark",
                        "parent_name": "Mrs E Clark PNE",
                        "family_name": "Clark",
                        "home_phone": "3870 9987",
                        "post_code": 4005,
                        "father_name": "Edward Clark",
                        "mobile1": "0427203657",
                        "address1": "",
                        "address3": "Addr Line 3",
                        "address2": "123 Smith Rd",
                        "address_description": "Correspondence",
                        "email2": "fang.guo@tassweb.com",
                        "work_phone": "3201 1302",
                        "state_code": "QLD",
                        "parent_code": "000055",
                        "address_number": 1,
                        "relationship": ""
                    },
                    {
                        "mobile2": "0461474255",
                        "town_suburb": "KENMORE HILLS",
                        "parent1": {
                            "initials": "L",
                            "suffix": "",
                            "surname": "Clason",
                            "description": "Mother/Parent 1",
                            "preferred_name": "Lili",
                            "other_name": "",
                            "title": "",
                            "first_name": "Lili"
                        },
                        "parent_name2": "",
                        "parent2": {
                            "initials": "R",
                            "suffix": "",
                            "surname": "Clason",
                            "description": "Father/Parent 2",
                            "preferred_name": "Reiley",
                            "other_name": "",
                            "title": "",
                            "first_name": "Reiley"
                        },
                        "email": "L.Clason@alphabus.com.au; R.Clason@alphabus.com.au",
                        "mother_name": "Lili Clason",
                        "country": "",
                        "salutation": "Mr & Mrs Clason",
                        "parent_name": "Reiley Clason",
                        "family_name": "Clason",
                        "home_phone": "07 3491 5382",
                        "post_code": 4069,
                        "father_name": "Reiley Clason",
                        "mobile1": "(M) 0455808472",
                        "address1": "",
                        "address3": "",
                        "address2": "680 Weiss Pl",
                        "address_description": "Father's Address",
                        "email2": "",
                        "work_phone": "M 07 3200 4485 F 07 3069 3714",
                        "state_code": "QLD",
                        "parent_code": "000511",
                        "address_number": 7,
                        "relationship": "Biological"
                    }
                ],
                "last_name": "Clark",
                "preferred_surname": "Clark",
                "first_name": "Andréa",
                "indigenous_status": "Aboriginal",
                "citizenship": "Visa Students",
                "dob": "02/09/1994",
                "preferred_name": "Andy",
                "other_name": "Joan",
                "gender": "F"
            }
        ]
    }
    ```
 
* **Error Response:**

    `commtype` not supplied
    ```javascript
      "__msg": "'commtype' IS REQUIRED"
    ```
    
* **Sample Parameters:**

  ```javascript
    commtype=ALL
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
    http://api.tasscloud.com.au/tassweb/api/?method=GetStudents&appcode=DEMOOE&company=10&token=THgDmy%2F7dWxUqvyAgjHHeg%3D%3D
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
      <input type="hidden" name="method" value="getStudents" />
      <input type="hidden" name="appcode" value="DEMOOE" />
      <input type="hidden" name="company" value="10" />
      <textarea name="token">THgDmy/7dWxUqvyAgjHHeg==</textarea>
    </form>
  ```
