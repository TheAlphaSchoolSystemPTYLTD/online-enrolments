**getStudents**
----
  Returns an array of structured student data in JSON format.

* **Version History:**

	TASS v54.4 - Method Added

* **Version:**

  3

* **Permission:**

    Student Records > Students - View

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
		"__tassversion":"01.000.043.0",
		"token":{
			"commtype":"ALL",
			"timestamp":"{ts '2021-03-04 12:22:32'}",
			"studcode":"0009999"
		},
		"students":[
			{
				"language":"Croatian",
				"nationality":"Turkey",
				"contacts":[
					{
						"mobile2":"0420221002",
						"town_suburb":"ALBION",
						"parent_name2":"",
						"m_initials":"P",
						"f_preferred_name":"Paula",
						"email":"t.sloman84@gmail.com",
						"m_preferred_name":"Paula",
						"mother_name":"Paula Clark",
						"country":"AUSTRALIA",
						"salutation":"Mr and Mrs Clark",
						"parent_name":"Mrs E Clark PNE Longer than the maximal limit 61 charactersXD",
						"family_name":"Clark",
						"m_title":"Mrs",
						"m_suffix":"suf",
						"f_suffix":"suf",
						"home_phone":"3870 9987",
						"post_code":4005,
						"father_name":"Edward Clark",
						"mobile1":"0420221002",
						"address1":"",
						"f_surname":"Clark",
						"address3":"Addr Line 3",
						"address2":"123 Smith Rd",
						"f_initials":"P",
						"address_description":"Correspondence",
						"f_description":"Father/Parent 2",
						"f_other_name":"PauOth",
						"email2":"fang.guo@tassweb.com",
						"f_title":"Mrs",
						"m_first_name":"Paula",
						"work_phone":"3201 1302",
						"state_code":"QLD",
						"parent_code":"000055",
						"address_number":1,
						"m_description":"Mother/Parent 1",
						"f_first_name":"Paula",
						"m_other_name":"PauOth",
						"m_surname":"Clark",
						"relationship":""
					}
				],
				"last_name":"Clark",
				"preferred_surname":"Clark",
				"first_name":"Andréa",
				"indigenous_status":"Aboriginal",
				"citizenship":"Visa Students",
				"dob":"02/09/1994",
				"preferred_name":"Andy",
				"other_name":"Joan",
				"gender":"F"
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
    {
        "commtype": "ALL",
		"studcode":"0009999"
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
