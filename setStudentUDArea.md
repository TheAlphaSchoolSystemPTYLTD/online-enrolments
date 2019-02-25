**SetStudentUDArea**
----
	Returns "success" and a count of updated students, or a structure of invalid validations "__invalid" belonging to student(s).

* **Version:**

	2

* **Method:**

	`GET | POST`
	
*  **Params:**

	**Required:**
 
	`id [string]` - student code.

	`area_code [string]` - area code.

	**Optional:**

	`eud1_flg [string] ` to `eud10_flg [string] ` - Flag Field 1 - 10

	`eud11_code [string]` to `eud20_code [string]` - Table Referend Field 11 - 20

	`eud21_text [string]` to `eud30_text [string]` - Text Field 21 - 30

	`eud31_date [date]` to `eud40_date [date]` - Date Field 31 - 40

	`eud41_attach_id [string]` to `eud50_attach_id [string]` - Attachment Field 41 - 50

	**Conditional:**

	`attachment_file [string]` - field is required where ‘attachment_file_name’ is supplied.

	`attachment_file_name [string]` - field is required where ‘attachment_file’ is supplied.

* **Success Response:**

	```javascript
	"success": "You successfully saved 1 student(s).",
	"token": {
		"timestamp": "{ts '2019-02-12 16:58:07'}",
		"area_code": 1,
		"studentudarea": [
			{
				"eud31_date": "2019-02-08",
				"eud21_text": "testing",
				"eud1_flg": "Y",
				"STUD_CODE": "0010090",
				"eud11_code": 10,
				"eud12_code": 890,
				"eud41_attach_id": "C5141223-DE66-686C-AC6701EAF7CE800F",
				"id": "0010090"
			}
		]
	}
	```
 
* **Error Response:**

	`studentudarea` not supplied
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

	`area_code` is not valid in table udtable
	```javascript
	__invalid: {
		"area_code": "Area code is not setup."
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

	`eud1_flg` [string] to `eud10_flg` [string] exceeds 1 character
	```javascript
	__invalid: {
		"[field]": "The value for this field exceeds the length permitted (2 of 1)."
	}
	```

	`eud1_flg` [string] to `eud10_flg` [string] is not an alphanumeric value fro A-Z and 0-9
	```javascript
	__invalid: {
		"[field]": "Value is not a valid alphanumeric code."
	}
	```

	`eud11_code` [string] to `eud20_code` [string] exceeds 3 characters
	```javascript
	__invalid: {
		"[field]": "exceeds 3 characters."
	}
	```

	`eud11_code` [string] to `eud20_code` [string] is not valid code
	```javascript
	__invalid: {
		"[field]": "The code is not valid."
	}
	```

	`eud21_text` [string] to `eud30_text` [string] exceeds 50 characters
	```javascript
	__invalid: {
		"[field]": "exceeds 50 characters."
	}
	```

	`eud31_date` [string] to `eud40_date` [string] is not in valid date format (yyyy-mm-dd)
	```javascript
	__invalid: {
		"[field]": "Value is not a valid date."
	}

	`eud41_attach_id` [string] to `eud50_attach_id` [string] is empty, or only one of attachment_file and attachment_file_name is passed in
	```javascript
	__invalid: {
		"[field]": "attachment_file and attachment_file_name are required if [field] is passed in."
	}
	```

	`eud41_attach_id` [string] to `eud50_attach_id` [string] attachment_file is passed in but attachment_file_name is not passed in
	```javascript
	__invalid: {
		"attachment_file_name": "attachment_file_name field is required where 'attachment_file' is supplied."
	}
	```

	`eud41_attach_id` [string] to `eud50_attach_id` [string] attachment_file_name is passed in but attachment_file is not passed in
	```javascript
	__invalid: {
		"attachment_file": "attachment_file field is required where 'attachment_file_name' is supplied."
	}
	```

	`eud41_attach_id` [string] to `eud50_attach_id` [string] attachment_file_name exceeds 255 characters
	```javascript
	__invalid: {
		"attachment_file_name": "attachment_file_name must be between 1 and 255 characters."
	}
	```

	`eud41_attach_id` [string] to `eud50_attach_id` [string] attachment_file is not base64 encoded
	```javascript
	__invalid: {
		"attachment_file": "attachment_file is not base64 encoded."
	}
	```

* **Sample Parameters:**

	```javascript
	{
		"area_code":"1",
		"studentudarea":
		[
			{
				"id":"0010090",
				"eud1_flg":"Y",
				"eud11_code":"10",
				"eud12_code":"890",
				"eud21_text":"testing",
				"eud31_date":"2019-02-08",
				"eud41_attach_id":
				{
					"attachment_file_name":"test",
					"attachment_file":"ClRoaXMgaXMgYSB0ZXN0IGZpbGUuCkRvIG5vdCBpbmNsdWRlIGEgdGFibGUhISEKTmFtZQlRdWFudGl0eQlWYWx1ZQppUGFkCTEJNTAwCmlQaG9uZQkxCTEwMDAKVG90YWwJMgkxNTAw"
				}
			}
		]
	}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	http://api.tasscloud.com.au/tassweb/api/?method=setStudentUDArea&appcode=DIGIENRO&company=10&v=2&token=BJVvYXC0We4Dtvp6Q49RqhBeAi6uqpTQ9t%2FKI9ZAFpCMeVXIFlDU5yNQIeYME%2BYLXgYA69RTUjXjLeVBetN6CaFMdPCKMWBXD%2Bkkt0%2Fuht0suYrSDONP6mx%2Fbt4WGgNOD5YoIYRNiIVDw2Qn2Oi5YodaEUgtGJohUJMzy3tqsX%2BraZk3j7d77okDCjb7MeFJ0DcupqUoRiGjE39415HTfPgNc6R6BY9wt7SJsj4yOPBrIxHQVS8Yy6gZ3nZgsJ5rhcdkB6eCI6b3FJ31s6vsVcbVu5NBY8AF1qqjWLMazduISzEBwRDsofXfJjo1KLX59R410bmbrF5Z7QZfEfE%2FlettTWOyb4EgdhBoC3v0aLOfF6Bt12AFXDo2VGbgryceeOLAscp%2FFr9ttH42hClBtWsxFU1N5dDENUsVHOwWcfCxd7aTtc0xjvaEYJWcZrRRZa1yrIvgeWaDk0LVxM5ePcT%2BltdrymgmxmZYgxdiYC1qQDcNXDx9hN7yKeZDUztwGA0yl2iXW8aBXAy5hRnztR0TrREyOba26mUHxUJO7tfpIyOrpPbE0nR18vtCZ%2BinbvyqN9adpZhQPByG2XD9M6MoYdmBCc3Duv9qb%2BIa0A8%3D
	```
	
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		 <input type="hidden" name="method" value="setStudentUDArea">
		 <input type="hidden" name="appcode" value="DIGIENRO">
		 <input type="hidden" name="company" value="10">
		 <input type="hidden" name="v" value="2">
		 <textarea name="token">BJVvYXC0We4Dtvp6Q49RqhBeAi6uqpTQ9t/KI9ZAFpCMeVXIFlDU5yNQIeYME+YLXgYA69RTUjXjLeVBetN6CaFMdPCKMWBXD+kkt0/uht0suYrSDONP6mx/bt4WGgNOD5YoIYRNiIVDw2Qn2Oi5YodaEUgtGJohUJMzy3tqsX+raZk3j7d77okDCjb7MeFJ0DcupqUoRiGjE39415HTfPgNc6R6BY9wt7SJsj4yOPBrIxHQVS8Yy6gZ3nZgsJ5rhcdkB6eCI6b3FJ31s6vsVcbVu5NBY8AF1qqjWLMazduISzEBwRDsofXfJjo1KLX59R410bmbrF5Z7QZfEfE/lettTWOyb4EgdhBoC3v0aLOfF6Bt12AFXDo2VGbgryceeOLAscp/Fr9ttH42hClBtWsxFU1N5dDENUsVHOwWcfCxd7aTtc0xjvaEYJWcZrRRZa1yrIvgeWaDk0LVxM5ePcT+ltdrymgmxmZYgxdiYC1qQDcNXDx9hN7yKeZDUztwGA0yl2iXW8aBXAy5hRnztR0TrREyOba26mUHxUJO7tfpIyOrpPbE0nR18vtCZ+inbvyqN9adpZhQPByG2XD9M6MoYdmBCc3Duv9qb+Ia0A8=</textarea>
	</form>
	```
