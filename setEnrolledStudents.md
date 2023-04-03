**SetEnrolledStudents**
----
	Returns "success" and a count of updated students, or a structure of invalid validations "__invalid" belonging to student(s).

* **Version History:**

	TASS v54.4 - Method Added

* **Version:**

	3

* **Permission:**

    Enrolments > Enrolments/Enrolled Student - Edit
    
* **Method:**

	`GET | POST`
	
*  **Params:**

	**Required:**
 
	`id [string]` - student code - Length must be between 1 and 8 Characters

	`surname [string]` - Student Surname - Length must be between 1 and 50 Characters

	`boarder [string]` - Is the Student a Boarder - Length must be 1 Character(Y/N)

	`entry_yr [integer]` - Year of Student Entry

	`entry_ygrp [integer]` - Student Year Group when Starting

	`sex [string]` - Student Gender - Length must be between 1 and 3 Characters

	`preferred_name [string]` - Student Preferred Name - Length must be between 1 and 50 Characters

	`prosp_flg [string]` - Stage 1 Flag - Length must be 1 Character(Y/N)

	`followup_flg [string]` - Stage 2 Flag - Length must be 1 Character(Y/N)

	`hold_paid [string]` - Stage 3 Flag - Length must be 1 Character(Y/N)

	`interview_flg [string]` - Stage 4 Flag - Length must be 1 Character(Y/N)

	`assess_flg [string]` - Stage 5 Flag - Length must be 1 Character(Y/N)

	`place_offered [string]` - Stage 6 Flag - Length must be 1 Character(Y/N)

	`accept_paid [string]` - Stage 7 Flag - Length must be 1 Character(Y/N)

	**Optional:**

	`preferred_surname [string]` - Student Preferred Surname (use surname if not supplied) - Length must be between 1 and 50 Characters
	
	`campus_code [string]` - Campus - Length must be between 1 and 3 Characters

	`curr_school [string]` - Current School - Length must be between 1 and 5 Characters

	`curr_year_grp [integer]` - Current Year Group

	`date_arrival [date dd/mm/yyyy or yyyy-mm-dd]` - Date of Arrival in Australia.

	`dob [date dd/mm/yyyy or yyyy-mm-dd]` - Date of Birth.

	`e_mail [string]` - Student Email - Length must be between 1 and 60 Characters

	`mob_phone [string]` - Student Mobile Phone - Length must be between 1 and 30 Characters

	`religion [string]` - Student Religion - Length must be between 1 and 2 Characters

	`resident_sts [string]` - Residency Status - Length must be between 1 and 3 Characters

	`visa_expiry [date dd/mm/yyyy]` - Student Visa Expiry

	`visa_subclass [string]` - Student Visa Subclass - Length must be between 1 and 6 Characters

	`sud1_flg to sud10_flg [string]` - Student user defined flag - Length must be 1 Character

	`sud11_code to sud20_code [string]` - Student user defined code - Length must be between 1 and 3 Characters

	`sud21_text to sud25_text [string]` - Student user defined text - Length must be between 1 and 20 Characters

	`usi [alphanumeric]` - Unique Student Identifier - Length must be under 10 Characters

	`addresses [array]` - An array of parents's address(es) associated with the enrolled student

	**Conditional:**

	`prosp_date [date dd/mm/yyyy or yyyy-mm-dd]` - Stage 1 date. Required if stage 1 Flag is set to "Y".

	`followup_date [date dd/mm/yyyy or yyyy-mm-dd]` - Stage 2 date. Required if stage 2 Flag is set to "Y".

	`hpaid_date [date dd/mm/yyyy or yyyy-mm-dd]` - Stage 3 date. Required if stage 3 Flag is set to "Y".

	`interview_date [date dd/mm/yyyy or yyyy-mm-dd]` - Stage 4 date. Required if stage 4 Flag is set to "Y".

	`assess_date [date dd/mm/yyyy or yyyy-mm-dd]` - Stage 5 date. Required if stage 5 Flag is set to "Y".

	`offer_date [date dd/mm/yyyy or yyyy-mm-dd]` - Stage 6 date. Required if stage 6 Flag is set to "Y".

	`accept_date [date dd/mm/yyyy or yyyy-mm-dd]` - Stage 7 date. Required if stage 7 Flag is set to "Y".

	`given_name [string]` - Student Given Names (invalid when `first_name` supplied, required when not supplied) - Length must be between 1 and 101 Characters

	`first_name [string]` - Student First Name (invalid when `given_name` supplied, required when not supplied) - Length must be between 1 and 50 Characters
	
	`other_name [string]` - Student Other name (pair with `first_name`, will get ignored if use with `given_name`) - Length must be between 1 and 50 Characters

	For item(s) in the `addresses` array:
	
	`add_num [string]` - Field is mandatory. Must be a valid add_num in "getParentAddressSetup".

	`par_name [string]` - Parent Name, field is mandatory.

	`par_name2 [string]` - Field is optional. (length limit 30 chars)

	`addr1 [string]` - Field is optional. (length limit 50 chars)

	`addr2 [string]` - Field is optional. (length limit 50 chars)

	`addr3 [string]` - Field is optional. (length limit 50 chars)

	`town_sub [string]` - Field is optional. (length limit 30 chars)

	`state_code [string]` - Field is optional. (length limit 3 chars)

	`post_code [string]` - Field is optional. (length limit 10 chars)

	`country [string]` - Field is optional. (length limit 20 chars)

	`dpid_text [string]` - Field is optional. (length limit 40 chars)

	`home_phone [string]` - Field is optional. (length limit 30 chars)

	`bus_phone [string]` - Field is optional. (length limit 30 chars)

	`fax [string]` - Field is optional. (length limit 30 chars)

	`salutation [string]` - Field is optional. (length limit 60 chars)

	`mobile1 [string]` - Field is optional. (length limit 30 chars)

	`sms_flg1 [string]` - Field is optional. (Y or N)

	`mobile2 [string]` - Field is optional. (length limit 30 chars)

	`sms_flg2 [string]` - Field is optional. (Y or N)
	
	`par_e_mail [string]` - Field is optional and must be a valid email address if supplied. (length limit 140 chars)
	
	`par_e_mail2 [string]` - Field is optional and must be a valid email address if supplied. (length limit 140 chars)

* **Success Response:**

	```javascript
	{
		"success": "You successfully saved 1 student(s).",
        "__tassversion": "01.053.3.000",
		"token": {
			"enrolledstudent": [
				{
					"resident_sts": "AUS",
					"sud21_text": "Visa79447",
					"sud1_flg": "Y",
					"curr_school": "EVT",
					"sud16_code": "CP",
					"accept_date": "2019-03-20 00:00:00.000",
					"followup_flg": "Y",
					"entry_ygrp": 7,
					"sud9_flg": 5,
					"dob": "1995-10-14 00:00:00.000",
					"boarder": "Y",
					"offer_date": "2018-01-01 00:00:00.000",
					"sud17_code": "SMK",
					"id": "0010245",
					"assess_flg": "Y",
					"sud3_flg": "N",
					"sud14_code": "FA",
					"sud11_code": "STP",
					"date_arrival": "2014-02-13 00:00:00.000",
					"preferred_surname": "Aardvaark",
					"accept_paid": "Y",
					"campus_code": "JU",
					"sud23_text": 1,
					"hold_paid": "Y",
					"religion": "AG",
					"visa_subclass": 123,
					"other_name": "Peter",
					"hpaid_date": "2018-01-01 00:00:00.000",
					"sud2_flg": 1,
					"visa_expiry": "2018-01-01 00:00:00.000",
					"mob_phone": "0420221002",
					"sud13_code": "SWI",
					"sud24_text": 2019,
					"sud5_flg": "N",
					"sex": "M",
					"sud10_flg": "Y",
					"sud19_code": "NOK",
					"assess_date": "2018-01-01 00:00:00.000",
					"followup_date": "2018-01-01 00:00:00.000",
					"first_name": "Ian",
					"sud4_flg": "N",
					"curr_year_grp": 8,
					"preferred_name": "Freddy",
					"interview_flg": "Y",
					"surname": "Aardvaark",
					"sud25_text": 1,
					"sud8_flg": "N",
					"sud7_flg": "N",
					"prosp_flg": "Y",
					"e_mail": "abc_news@abc.com",
					"sud22_text": "Passport44119",
					"sud18_code": 30,
					"sud15_code": "EXA",
					"STUD_CODE": "0010245",
					"place_offered": "Y",
					"sud6_flg": "Y",
					"prosp_date": "2018-01-01 00:00:00.000",
					"interview_date": "2018-01-01 00:00:00.000",
					"entry_yr": 2021,
					"sud12_code": "AUS",
					"sud20_code": "ABC"
				}
			]
		}
	}
	```
 
* **Error Response:**

	`enrolledstudent` not supplied
	```javascript
	__invalid: {
		"enrolledstudent": "'enrolledstudent' is required."
	}
	```

	`[field_name]` is not valid
	```javascript
	__invalid: {
		"[field_name]": "'[field_name]' is not a valid field name"
	}
	```

	`id` not supplied
	```javascript
	__invalid: {
		"id": "Id is required for all rows."
	}
	```

	`id` has a duplicate value
	```javascript
	__invalid: {
		"id": "Id must be unique for all rows."
	}
	```

	`id` length longer than 8
	```javascript
	__invalid: {
		"id": "exceeds 8 characters."
	}
	```

	`id` not a valid student code in table d3_enrolments
	```javascript
	__invalid: {
		"stud_code": "Enrolled student not in staging table."
	}
	```

	`id` not a valid student code in table studenrol
	```javascript
	__invalid: {
		"stud_code": "Enrolled student not in TASS."
	}
	```

	`id` is a valid student code in table studenrol where canc_flg = "Y"
	```javascript
	__invalid: {
		"stud_code": "Enrolled student has been cancelled."
	}
	```

	`id` is a valid student code in table studenrol where tran_sts = "T"
	```javascript
	__invalid: {
		"stud_code": "Enrolled student has been transferred to Current."
	}
	```

	`boarder` is not Y or N
	```javascript
	__invalid: {
		"boarder": "Boarder must be either Y or N."
	}
	```

	`surname` exceeds 30 characters
	```javascript
	__invalid: {
		"surname": "surname exceeds 30 characters."
	}
	```

	`boarder` is not Y or N
	```javascript
	__invalid: {
		"boarder": "Boarder must be either Y or N."
	}
	```

	`entry_yr` have value less than current year
	```javascript
	__invalid: {
		"entry_yr": "must be greater than or equal to [current_year]."
	} 
	```

	`entry_yr` have value greater than 2100
	```javascript
	__invalid: {
		"entry_yr": "must be less than or equal to 2100."
	} 
	```

	`curr_year_grp` have value less than -3
	```javascript
	__invalid: {
		"curr_year_grp": "must be greater than or equal to [current_year]."
	} 
	```

	`curr_year_grp` have value greater than 16
	```javascript
	__invalid: {
		"curr_year_grp": "must be less than or equal to 16."
	} 
	```

	`entry_ygrp` have value less than [Minimum Year Group] in Parent Setup
	```javascript
	__invalid: {
		"entry_ygrp": "must be greater than or equal to [Minimum Year Group]."
	} 
	```

	`entry_ygrp` have value greater than [Maximum Year Group] in Parent Setup
	```javascript
	__invalid: {
		"entry_ygrp": "must be less than or equal to [Maximum Year Group]."
	} 
	```

	`sex` is not M or F
	```javascript
	__invalid: {
		"sex": "sex must be either M or F."
	}
	```

	`given_name` exceeds 101 characters
	```javascript
	__invalid: {
		"given_name": "given_name exceeds 101 characters."
	}
	```

	`preferred_name` exceeds 20 characters
	```javascript
	__invalid: {
		"preferred_name": "preferred_name exceeds 20 characters."
	}
	```

	`campus_code` exceeds 3 characters
	```javascript
	__invalid: {
		"campus_code": "campus_code exceeds 3 characters."
	}
	```

	`campus_code` is not a valid code in campus table
	```javascript
	__invalid: {
		"campus_code": "<campus_code from file> is not a valid campus code."
	} 
	```

	`curr_school` exceeds 5 characters
	```javascript
	__invalid: {
		"curr_school": "curr_school exceeds 5 characters."
	}
	```

	`curr_school` is not a valid code in feedschool table
	```javascript
	__invalid: {
		"curr_school": "<curr_school from file> is not a valid school code."
	} 
	```

	`date_arrival` is not in date format
	```javascript
	__invalid: {
		"date_arrival": "Value is not a valid <strong>date</strong>."
	} 
	```

	`dob` is not in date format
	```javascript
	__invalid: {
		"dob": "Value is not a valid <strong>date</strong>."
	} 
	```

	`e_mail` is not in valid email address format
	```javascript
	__invalid: {
		"e_mail": "invalid email address"
	} 
	```

	`mob_phone` exceeds 30 characters
	```javascript
	__invalid: {
		"mob_phone": "mob_phone exceeds 30 characters."
	}
	```

	`religion` exceeds 2 characters
	```javascript
	__invalid: {
		"religion": "religion exceeds 2 characters."
	}
	```

	`religion` is not a valid code in religion table
	```javascript
	__invalid: {
		"religion": "<religion from file> is not a valid religion code."
	} 
	```

	`resident_sts` exceeds 3 characters
	```javascript
	__invalid: {
		"resident_sts": "resident_sts exceeds 3 characters."
	}
	```

	`resident_sts` is not a valid code in resident_sts table
	```javascript
	__invalid: {
		"resident_sts": "<resident_sts from file> is not a valid resident status code."
	} 
	```

	`visa_expiry` is not in date format
	```javascript
	__invalid: {
		"visa_expiry": "Value is not a valid <strong>date</strong>."
	} 
	```

	`visa_subclass` exceeds 6 characters
	```javascript
	__invalid: {
		"visa_subclass": "visa_subclass exceeds 6 characters."
	}
	```

	For stage flags: prosp_flg, followup_flg, hold_paid, interview_flg, assess_flg, place_offered, accept_paid

	`[stage_flg]` exceed 1 characters
	```javascript
	__invalid: {
		"[stage_flg]": "exceeds 1 characters."
	} 
	```

	`[stage_flg]` is not "Y" or "N"
	```javascript
	__invalid: {
		"[stage_flg]": "[stage_flg] must be either Y or N."
	} 
	```

	For stage dates: prosp_date, followup_date, hpaid_date, interview_date, assess_date, offer_date, accept_date

	`[stage_date]` is not in date format
	```javascript
	__invalid: {
		"[stage_date]": "Value is not a valid <strong>date</strong>."
	} 
	```

	`sud1_flg` to `sud10_flg` exceeds 1 characters
	```javascript
	__invalid: {
		"[field]": "[field] exceeds [field's length limit] characters."
	}
	```

	`sud1_flg` to `sud10_flg` is not a valid value from [A-Z and 0-9]
	```javascript
	__invalid: {
		"[field]": "Value is not a valid <strong>alphanumeric code</strong>."
	}
	```

	`sud11_code` to `sud20_code` exceeds 3 characters
	```javascript
	__invalid: {
		"[field]": "[field] exceeds [field's length limit] characters."
	}
	```

	`sud11_code` to `sud20_code` is not set up in table udtable
	```javascript
	__invalid: {
		"[field]": "[field] is not a valid ud field."
	}
	```

	`sud20_text` to `sud25_text` exceeds 20 characters
	```javascript
	__invalid: {
		"[field]": "[field] exceeds [field's length limit] characters."
	}
	```

	`first_name` exceeds 50 characters
	```javascript
	__invalid: {
		"first_name": "first_name exceeds 50 characters."
	}
	```

	`other_name` exceeds 50 characters
	```javascript
	__invalid: {
		"other_name": "other_name exceeds 50 characters."
	}
	```

	`preferred_surname` exceeds 50 characters
	```javascript
	__invalid: {
		"preferred_surname": "preferred_surname exceeds 50 characters."
	}
	```

	`given_name` and `first_name` not supplied
	```javascript
	__invalid: {
		"given_name": "given_name required when first_name not supplied."
	}
	```

	`given_name` and `first_name` both supplied
	```javascript
	__invalid: {
		"given_name": "given_name invalid when first_name supplied."
	}
	```

	`usi` exceeds 10 characters
	```javascript
	__invalid: {
		"usi": "USI must be under 10 characters."
	}
	```

	`usi` using non-alphanumeric character such as special characters
	```javascript
	__invalid: {
		"usi": "USI must be alphanumeric."
	}
	```

	`addresses` must be an array
	```javascript
	__invalid: {
		"addresses": "must be an array."
	}
	```

	`add_num` is required for each array item in addresses
	```javascript
	__invalid: {
		"enrolledstudents.[stud_code].addresses.[x].add_num": "[add_num] is not a valid Address Number."
	}
	```

	`par_name` is required for each array item in addresses
	```javascript
	__invalid: {
		"enrolledstudents.[stud_code].addresses.[x].add_num": "Parent Name must be specified."
	}
	```

	`sms_flg1` must be Y or N if supplied
	```javascript
	__invalid: {
		"enrolledstudents.[stud_code].addresses.[x].sms_flg1": "Value must be Y/N."
	}
	```

	`sms_flg2` must be Y or N if supplied
	```javascript
	__invalid: {
		"enrolledstudents.[stud_code].addresses.[x].sms_flg2": "Value must be Y/N."
	}
	```

	`par_e_mail` exceeds 140 characters
	```javascript
	__invalid: {
		"enrolledstudents.[stud_code].addresses.[x].add_num": "par_e_mail cannot be longer than 140 characters."
	}
	```

	`par_e_mail` must be in email format
	```javascript
	__invalid: {
		"enrolledstudents.[stud_code].addresses.[x].add_num": "par_e_mail is invalid."
	}
	```

	`par_e_mail2` exceeds 140 characters
	```javascript
	__invalid: {
		"enrolledstudents.[stud_code].addresses.[x].add_num": "par_e_mail2 cannot be longer than 140 characters."
	}
	```

	`par_e_mail2` must be in email format
	```javascript
	__invalid: {
		"enrolledstudents.[stud_code].addresses.[x].add_num": "par_e_mail2 is invalid."
	}
	```

* **Sample Parameters:**

	```javascript
	{
		"enrolledstudent":
		[
			{
				"id":"0010245",
				"surname":"Aardvaark",
				"boarder":"Y",
				"campus_code":"JU",
				"curr_school":"EVT",
				"curr_year_grp":"8",
				"date_arrival":"2014-02-13 00:00:00.000",
				"dob":"1995-10-14 00:00:00.000",
				"e_mail":"abc_news@abc.com",
				"entry_yr":"2021",
				"entry_ygrp":"7",
				"sex":"M",
				"mob_phone":"0420221002",
				"preferred_name":"Freddy",
				"religion":"AG",
				"resident_sts":"AUS",
				"visa_expiry":"2018-01-01 00:00:00.000",
				"visa_subclass":"123",
				"prosp_flg":"Y",
				"prosp_date":"2018-01-01 00:00:00.000",
				"followup_flg":"Y",
				"followup_date":"2018-01-01 00:00:00.000",
				"hold_paid":"Y",
				"hpaid_date":"2018-01-01 00:00:00.000",
				"interview_flg":"Y",
				"interview_date":"2018-01-01 00:00:00.000",
				"assess_flg":"Y",
				"assess_date":"2018-01-01 00:00:00.000",
				"place_offered":"Y",
				"offer_date":"2018-01-01 00:00:00.000",
				"accept_paid":"Y",
				"accept_date":"2019-03-20 00:00:00.000",
				"sud1_flg":"Y",
				"sud2_flg":"1",
				"sud3_flg":"N",
				"sud4_flg":"N",
				"sud5_flg":"N",
				"sud6_flg":"Y",
				"sud7_flg":"N",
				"sud8_flg":"N",
				"sud9_flg":"5",
				"sud10_flg":"Y",
				"sud11_code":"STP",
				"sud12_code":"AUS",
				"sud13_code":"SWI",
				"sud14_code":"FA ",
				"sud15_code":"EXA",
				"sud16_code":"CP ",
				"sud17_code":"SMK",
				"sud18_code":"30",
				"sud19_code":"NOK",
				"sud20_code":"ABC",
				"sud21_text":"Visa79447",
				"sud22_text":"Passport44119 ",
				"sud23_text":"1",
				"sud24_text":"2019",
				"sud25_text":"1",
				"first_name" : "Ian",
				"other_name" : "Peter",
				"preferred_surname" : "Aardvaark",
				"addresses": [{
				    "add_num": "2",
				    "par_name": "The Aardvaarks",
				    "town_sub": "Mt Gravatt",
				    "state_code": "QLD",
				    "post_code": "4122"
				},
				{
				    "add_num": "3",
				    "par_name": "The Aardvaark's Business",
				    "town_sub": "Mt Gravatt",
				    "state_code": "QLD",
				    "post_code": "4122"
				}

			    ]
			}
		]
	}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	http://api.tasscloud.com.au/tassweb/api/?method=setEnrolledStudents&appcode=DIGIENRO&company=10&v=2&token=BJVvYXC0We4Dtvp6Q49RqhBeAi6uqpTQ9t%2FKI9ZAFpCMeVXIFlDU5yNQIeYME%2BYLXgYA69RTUjXjLeVBetN6CaFMdPCKMWBXD%2Bkkt0%2Fuht0suYrSDONP6mx%2Fbt4WGgNOD5YoIYRNiIVDw2Qn2Oi5YodaEUgtGJohUJMzy3tqsX%2BraZk3j7d77okDCjb7MeFJ0DcupqUoRiGjE39415HTfPgNc6R6BY9wt7SJsj4yOPBrIxHQVS8Yy6gZ3nZgsJ5rhcdkB6eCI6b3FJ31s6vsVcbVu5NBY8AF1qqjWLMazduISzEBwRDsofXfJjo1KLX59R410bmbrF5Z7QZfEfE%2FlettTWOyb4EgdhBoC3v0aLOfF6Bt12AFXDo2VGbgryceeOLAscp%2FFr9ttH42hClBtWsxFU1N5dDENUsVHOwWcfCxd7aTtc0xjvaEYJWcZrRRZa1yrIvgeWaDk0LVxM5ePcT%2BltdrymgmxmZYgxdiYC1qQDcNXDx9hN7yKeZDUztwGA0yl2iXW8aBXAy5hRnztR0TrREyOba26mUHxUJO7tfpIyOrpPbE0nR18vtCZ%2BinbvyqN9adpZhQPByG2XD9M6MoYdmBCc3Duv9qb%2BIa0A8%3D
	```
	
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		 <input type="hidden" name="method" value="setEnrolledStudents">
		 <input type="hidden" name="appcode" value="DIGIENRO">
		 <input type="hidden" name="company" value="10">
		 <input type="hidden" name="v" value="2">
		 <textarea name="token">BJVvYXC0We4Dtvp6Q49RqhBeAi6uqpTQ9t/KI9ZAFpCMeVXIFlDU5yNQIeYME+YLXgYA69RTUjXjLeVBetN6CaFMdPCKMWBXD+kkt0/uht0suYrSDONP6mx/bt4WGgNOD5YoIYRNiIVDw2Qn2Oi5YodaEUgtGJohUJMzy3tqsX+raZk3j7d77okDCjb7MeFJ0DcupqUoRiGjE39415HTfPgNc6R6BY9wt7SJsj4yOPBrIxHQVS8Yy6gZ3nZgsJ5rhcdkB6eCI6b3FJ31s6vsVcbVu5NBY8AF1qqjWLMazduISzEBwRDsofXfJjo1KLX59R410bmbrF5Z7QZfEfE/lettTWOyb4EgdhBoC3v0aLOfF6Bt12AFXDo2VGbgryceeOLAscp/Fr9ttH42hClBtWsxFU1N5dDENUsVHOwWcfCxd7aTtc0xjvaEYJWcZrRRZa1yrIvgeWaDk0LVxM5ePcT+ltdrymgmxmZYgxdiYC1qQDcNXDx9hN7yKeZDUztwGA0yl2iXW8aBXAy5hRnztR0TrREyOba26mUHxUJO7tfpIyOrpPbE0nR18vtCZ+inbvyqN9adpZhQPByG2XD9M6MoYdmBCc3Duv9qb+Ia0A8=</textarea>
	</form>
	```
