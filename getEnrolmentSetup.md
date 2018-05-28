**getEnrolmentSetup**
----
	Returns a structured Enrolment Setup data including enrolment, student and fee information in JSON format.
	
* **Version History:**

	TASS v48.2 - Method Included
	
	TASS v49.4 - Method Added

* **Version:**

	2

* **Method:**

	`GET | POST`
  
* **Params:**

   **Required:**
 
	`includeenrolmentonly [boolean]` - Include Enrolment information only                    

   **Optional:**

	none

   **Conditional:**

	none

* **Success Response:**

    ```javascript
    "setup": {
		"student": {
			"contact_name": "Archy Bigglesworth",
			"commrules_enabled": "Y",
			"order_flg": "N",
			"semester_short": "Sem",
			"contact_url": "",
			"year_zero": "P",
			"contact_fax": "",
			"contact_phone": "",
			"mm_flg": "Y",
			"year_negthree": "BB",
			"dol_flg": "N",
			"stud_code_fmt": 9999999,
			"default_sex": "",
			"auto_num_flg": true,
			"semester_text": "Semester",
			"aliases": "Y",
			"contact_email": "biggles@tassweb.com.au",
			"year_negtwo": "AA",
			"year_negone": "PK",
			"semester_max": 2
		},
		"fee": {
			"other2_bank_code": "",
			"next_intern_code": -1,
			"bill_prds": 30,
			"surchg_acct_code": "",
			"bf_pl_calc": "",
			"bld_acct_code": "01-0930-00-00",
			"rec_printer_id": "lp01",
			"other2_acct_code": "01-0290-00-00",
			"other5_bank_code": "",
			"other1_desc": "Enrol Deposit",
			"fee_addr": 3,
			"def_addr": 1,
			"post_rec_detl": "D",
			"cash_jour_code": "CR",
			"sfl_flg": "Y",
			"payment_days": 0,
			"contact_phone": "3216 0999",
			"other3_bank_code": "",
			"plstatement_flg": "A",
			"upd_build_amt": "Y",
			"other3_desc": "Fees in Advance",
			"other3_acct_code": "01-8100-00-00",
			"cash_acct_code": "01-6100-00-00",
			"last_post_date": "2018-01-16 00:00:00.0",
			"auto_num_flg": "Y",
			"sender_email": "",
			"contact_email": "",
			"stat_fmt": 33,
			"next_auto_num": "002152",
			"contact_url": "www.parentaccounts.com.au",
			"other4_bank_code": "",
			"bld_flg": "D",
			"other4_acct_code": "01-0410-00-00",
			"bf_rec_mess": "Voluntary Building Fund donation to Somerville House Building Fund\r\n\r\nYour financial involvement reinforces and recognises the support provided by past families and members of the current School community by providing assistance with the School's ongoing development programs.  We are most appreciative of your investment in the School's future.\r\n\r\nSection 30-15 of the Income Tax Assessment Act 1997 allows for tax deductibility for this gift.  Please use this letter as an official receipt for taxation purposes.",
			"disc_acct_code": "01-0130-00-00",
			"ar_acct_code": "01-6200-00-00",
			"bld_amt": 50,
			"email_text": "",
			"tax_acct_code": "01-4091-00-00",
			"depref_jour_code": "REF",
			"other4_desc": "Bookshop",
			"contact_name": "Steven Bursar",
			"cc_email": "",
			"split_rcpt_flg": "N",
			"par_code_fmt": 999999,
			"next_bank_dep_num": 150,
			"other2_desc": "Enrol Applic. Fee*",
			"next_chg_num": 149650,
			"contact_fax": "3216 0500",
			"stmt_disc_per": 0,
			"other5_acct_code": "01-0420-00-00",
			"other5_desc": "Canteen",
			"remind_fmt": "L",
			"rec_print_imm": "P",
			"sales_jour_code": "FJ",
			"other1_acct_code": "01-8610-00-00",
			"plbalance_flg": "L",
			"other1_bank_code": "",
			"bf_pl_label": "",
			"rec_sort_flg": "A"
		},
		"enrolment": {
			"contact_name": "Sevlar Vorumchack",
			"commtype_code": "TK",
			"par_code_fmt": 999999,
			"pref_flg": "N",
			"contact_url": "www.Svorumchack.com.au",
			"contact_fax": "a",
			"auto_xfer_flg": "Y",
			"contact_phone": "a",
			"tfer_notes": "Y",
			"stud_code_fmt": 9999999,
			"use_receipts": "Y",
			"transfer_deposits": "Y",
			"adv_fee_acct": "01-8100-00-00"
		}
	}
    ```
 
* **Error Response:**

    Required `includeenrolmentonly` not supplied.
	```javascript
	"__invalid": {
		"includeenrolmentonly": "field is required"
	}
	```
	
	Bool `includeenrolmentonly` not a valid bool.
	```javascript
	"__invalid": {
		"includeenrolmentonly": "Value is not a valid boolean."
	}
	```
    
* **Sample Parameters:**

	```javascript
	{"includeenrolmentonly":"false"}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	https://api.tasscloud.com.au/tassweb/api/?appcode=DEMOOE&v=2&method=GetEnrolmentSetup&token=queKxGSB6mqjLBTnIbKMis7T5t325qzTd63o3vWRs66biSN5GZVZJ9BXHdqHfiEt&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="https://api.tasscloud.com.au/tassweb/api/">
		<input type="hidden" name="method" value="GetEnrolmentSetup">
		<input type="hidden" name="appcode" value="DEMOOE">
		<input type="hidden" name="company" value="10">
		<input type="hidden" name="v" value="2">
		<textarea name="token">queKxGSB6mqjLBTnIbKMis7T5t325qzTd63o3vWRs66biSN5GZVZJ9BXHdqHfiEt</textarea>
	</form>
	```
