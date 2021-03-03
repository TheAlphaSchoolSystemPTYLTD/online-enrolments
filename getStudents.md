**getStudents**
----
  Returns an array of structured student data in JSON format.

* **Version History:**

    TASS v55.0 - Method Added

* **Version:**

  3

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
			"students": [
					{
						"language": "",
						"nationality": "",
						"contacts": [
							{
								"mobile2": "",
								"town_suburb": "LUTWYCHE",
								"parent_name2": "",
								"m_initials": "M",
								"f_preferred_name": "Mary",
								"email": "",
								"m_preferred_name": "Mary",
								"mother_name": "Mary Agnew",
								"country": "",
								"salutation": "",
								"parent_name": "Mr & Mrs G. Agnew",
								"family_name": "Agnew",
								"m_title": "",
								"m_suffix": "",
								"f_suffix": "",
								"home_phone": "374 2252",
								"post_code": 4030,
								"father_name": "George Agnew",
								"mobile1": "0612016500",
								"address1": "",
								"f_surname": "Agnew",
								"address3": "",
								"address2": "1/54 Kitchener Road",
								"f_initials": "M",
								"address_description": "Postal",
								"f_description": "Father/Parent 2",
								"f_other_name": "",
								"email2": "",
								"f_title": "",
								"m_first_name": "Mary",
								"work_phone": "221 9898",
								"state_code": "QLD",
								"parent_code": "000003",
								"address_number": 1,
								"m_description": "Mother/Parent 1",
								"f_first_name": "Mary",
								"m_other_name": "",
								"m_surname": "Agnew",
								"relationship": ""
							},
							{
								"mobile2": "",
								"town_suburb": "STAFFORD HEIGHTS",
								"parent_name2": "",
								"m_initials": "M",
								"f_preferred_name": "Mary",
								"email": "Butler@alphabus.com.au",
								"m_preferred_name": "Mary",
								"mother_name": "Mary Agnew",
								"country": "",
								"salutation": "",
								"parent_name": "Mr & Mrs G Butler",
								"family_name": "Agnew",
								"m_title": "",
								"m_suffix": "",
								"f_suffix": "",
								"home_phone": "",
								"post_code": 4053,
								"father_name": "George Agnew",
								"mobile1": "0612016500",
								"address1": "31 Tasman St",
								"f_surname": "Agnew",
								"address3": "Street3",
								"address2": "Street 2",
								"f_initials": "M",
								"address_description": "Residential",
								"f_description": "Father/Parent 2",
								"f_other_name": "",
								"email2": "",
								"f_title": "",
								"m_first_name": "Mary",
								"work_phone": "",
								"state_code": "QLD",
								"parent_code": "000003",
								"address_number": 2,
								"m_description": "Mother/Parent 1",
								"f_first_name": "Mary",
								"m_other_name": "",
								"m_surname": "Agnew",
								"relationship": ""
							}
						],
						"last_name": "Agnew",
						"preferred_surname": "Agnew",
						"first_name": "Edith Nell Blue Healer Bitzer",
						"indigenous_status": "",
						"citizenship": "Australian Citizen",
						"dob": "02/05/1988",
						"preferred_name": "Edie",
						"other_name": "Edith Nell Other Bell Nell",
						"gender": "U"
					}
			],
			"__status": "success",
			"__tassversion": "01.000.043.0",
			"__invalid": {},
			"__locks": {},
			"token": {
					"commtype": "ALL",
					"timestamp": "{ts '2021-01-19 11:36:19'}"
			}
		}		
    ```
 
* **Error Response:**

    `commtype` not supplied
    ```javascript
      "__msg": "'commtype' IS REQUIRED"
    ```
    
* **Sample Parameters:**

  ```javascript
    {
        "commtype": "ALL"
    }
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
