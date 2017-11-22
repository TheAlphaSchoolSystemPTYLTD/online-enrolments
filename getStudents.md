**getStudents**
----
  Returns an array of structured student data in JSON format.

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
      "students": [
        {
            "language": "French",
            "nationality": "Australia",
            "contacts": [
                {
                    "mobile2": "",
                    "town_suburb": "KEDRON",
                    "address_description": "Correspondence",
                    "parent_name2": "",
                    "email": "bell@nowhere.com.au",
                    "work_phone": "3456 8711",
                    "state_code": "QLD",
                    "mother_name": "Lyn Bell",
                    "parent_code": 10018,
                    "address_number": 1,
                    "country": "",
                    "salutation": "Mrs Bell",
                    "parent_name": "Mrs L Bell",
                    "family_name": "Bell",
                    "home_phone": "3856 4321",
                    "post_code": 4031,
                    "relationship": "",
                    "father_name": "Steven Bell",
                    "mobile1": "0413443651",
                    "address1": "",
                    "address3": "",
                    "address2": "PO Box 4"
                },
                {
                    "mobile2": "",
                    "town_suburb": "KEDRON",
                    "address_description": "Mother",
                    "parent_name2": "",
                    "email": "bell@nowhere.com.au",
                    "work_phone": "3456 8711",
                    "state_code": "QLD",
                    "mother_name": "Lyn Bell",
                    "parent_code": 10018,
                    "address_number": 4,
                    "country": "",
                    "salutation": "Mrs Bell",
                    "parent_name": "Mrs L Bell",
                    "family_name": "Bell",
                    "home_phone": "3856 4321",
                    "post_code": 4031,
                    "relationship": "Biological",
                    "father_name": "Steven Bell",
                    "mobile1": "0413443651",
                    "address1": "",
                    "address3": "",
                    "address2": "PO Box 4"
                }
            ],
            "citizenship": "Australian Citizen",
            "dob": "03/12/1994",
            "preferred_name": "Mattie",
            "gender": "M",
            "last_name": "Bell",
            "first_name": "Mathew James",
            "indigenous_status": "Aboriginal & T S I"
        }
      ]
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
