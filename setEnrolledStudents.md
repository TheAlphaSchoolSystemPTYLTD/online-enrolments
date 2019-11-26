**SetEnrolledStudents**
----
	Returns "success" and a count of updated students, or a structure of invalid validations "__invalid" belonging to student(s).

* **Version History:**

    TASS v52.0 - Add 3 new optional fields `first_name`, `other_name`, `preferred_surname`.

* **Version:**

	2
    
* **Method:**

	`GET | POST`
	
*  **Params:**

	**Required:**
 
	`id [string]` - student code.

	`surname [string]` - Surname.

	`boarder [string]` - Boarder.

	`entry_yr [string]` - Entry Year.

	`entry_ygrp [string]` - Entry Year Group.

	`sex [string]` - Gender.

	`given_name [string]` - Given Names.

	`preferred_name [string]` - Preferred Name.

	`prosp_flg [string]` - Stage 1 flag.

	`followup_flg [string]` - Stage 2 flag.

	`hold_paid [string]` - Stage 3 flag.

	`interview_flg [string]` - Stage 4 flag.

	`assess_flg [string]` - Stage 5 flag.

	`place_offered [string]` - Stage 6 flag.

	`accept_paid [string]` - Stage 7 flag.

	**Optional:**

	`first_name [string]` - First Name.

	`other_name [string]` - Other Name.

	`preferred_surname [string]` - Preferred Surname.
	
	`campus_code [string]` - Campus.

	`curr_school [string]` - Current School.

	`curr_year_grp [string]` - Current Year Group.

	`date_arrival [date dd/mm/yyyy or yyyy-mm-dd]` - Date of Arrival in Australia.

	`dob [date dd/mm/yyyy or yyyy-mm-dd]` - Date of Birth.

	`e_mail [string]` - Email.

	`mob_phone [string]` - Mobile Phone.

	`religion [string]` - Religion.

	`resident_sts [string]` - Residency Status.

	`visa_expiry [string]` - Visa Expiry Date.

	`visa_subclass [string]` - Visa Subclass.

	`sud1_flg [string]` to `sud9_flg [string]` - UD Flag Field 1 - 10.

	`sud11_code [string]` to `sud20_code [string]` - Table Reference Fields 11 - 20.

	`sud21_text [string]` to `sud25_text [string]` - Table Reference Fields 20 - 25.

	**Conditional:**

	`prosp_date [date dd/mm/yyyy or yyyy-mm-dd]` - Stage 1 date. Required if stage 1 Flag is set to "Y".

	`followup_date [date dd/mm/yyyy or yyyy-mm-dd]` - Stage 2 date. Required if stage 2 Flag is set to "Y".

	`hpaid_date [date dd/mm/yyyy or yyyy-mm-dd]` - Stage 3 date. Required if stage 3 Flag is set to "Y".

	`interview_date [date dd/mm/yyyy or yyyy-mm-dd]` - Stage 4 date. Required if stage 4 Flag is set to "Y".

	`assess_date [date dd/mm/yyyy or yyyy-mm-dd]` - Stage 5 date. Required if stage 5 Flag is set to "Y".

	`offer_date [date dd/mm/yyyy or yyyy-mm-dd]` - Stage 6 date. Required if stage 6 Flag is set to "Y".

	`accept_date [date dd/mm/yyyy or yyyy-mm-dd]` - Stage 7 date. Required if stage 7 Flag is set to "Y".

* **Success Response:**

	```javascript
	{
		"success": "You successfully saved 1 student(s).",
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
					"given_name": "Ian Peter",
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
					"entry_yr": 2019,
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

	`surname [string]` exceeds 30 characters
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

	`entry_ygrp` have value less than -3
	```javascript
	__invalid: {
		"entry_ygrp": "must be greater than or equal to -3."
	} 
	```

	`sex` is not M or F
	```javascript
	__invalid: {
		"sex": "sex must be either M or F."
	}
	```

	`given_name [string]` exceeds 30 characters
	```javascript
	__invalid: {
		"given_name": "given_name exceeds 30 characters."
	}
	```

	`preferred_name [string]` exceeds 20 characters
	```javascript
	__invalid: {
		"preferred_name": "preferred_name exceeds 20 characters."
	}
	```

	`campus_code [string]` exceeds 3 characters
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

	`curr_school [string]` exceeds 5 characters
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

	`mob_phone [string]` exceeds 30 characters
	```javascript
	__invalid: {
		"mob_phone": "mob_phone exceeds 30 characters."
	}
	```

	`religion [string]` exceeds 2 characters
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

	`resident_sts [string]` exceeds 3 characters
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

	`visa_subclass [string]` exceeds 6 characters
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

	`sud1_flg` [string] to `sud10_flg` [string] exceeds 1 characters
	```javascript
	__invalid: {
		"[field]": "[field] exceeds [field's length limit] characters."
	}
	```

	`sud1_flg` [string] to `sud10_flg` [string] is not a valid value from [A-Z and 0-9]
	```javascript
	__invalid: {
		"[field]": "Value is not a valid <strong>alphanumeric code</strong>."
	}
	```

	`sud11_code` [string] to `sud20_code` [string] exceeds 3 characters
	```javascript
	__invalid: {
		"[field]": "[field] exceeds [field's length limit] characters."
	}
	```

	`sud11_code` [string] to `sud20_code` [string] is not set up in table udtable
	```javascript
	__invalid: {
		"[field]": "[field] is not a valid ud field."
	}
	```

	`sud20_text` [string] to `sud25_text` [string] exceeds 20 characters
	```javascript
	__invalid: {
		"[field]": "[field] exceeds [field's length limit] characters."
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
				"entry_yr":"2019",
				"entry_ygrp":"7",
				"sex":"M",
				"given_name":"Ian Peter",
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
				"preferred_surname" : "Aardvaark"
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
