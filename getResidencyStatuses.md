**getResidencyStatuses**
----
	Returns an array of structured residency status data in JSON format.
	
* **Version History:**

	TASS v49.1 - Method Added

* **Version:**

	1

* **Method:**

	`GET | POST`
  
* **Params:**

   **Required:**
 
	`codeonly [boolean]` - Return Code only. Must be 'true' or 'false'.                    

   **Optional:**

	none

   **Conditional:**

	none

* **Success Response:**

    ```javascript
    "statuses": [
		{
			"census_flg": "Y",
			"code": "AUS",
			"expcode": "",
			"citizen_flg": "Y",
			"permres_flg": "N",
			"res_exp_code": "",
			"desc": "Australian Citizen"
		},
		{
			"census_flg": "Y",
			"code": "PR",
			"expcode": "",
			"citizen_flg": "N",
			"permres_flg": "Y",
			"res_exp_code": "",
			"desc": "Australian Permanent Resident"
		},
		{
			"census_flg": "N",
			"code": "FFS",
			"expcode": "FULLFEESTUD",
			"citizen_flg": "N",
			"permres_flg": "N",
			"res_exp_code": "FULLFEESTUD",
			"desc": "Full Fee paying Overseas Student"
		},
		{
			"census_flg": "N",
			"code": "IMP",
			"expcode": "",
			"citizen_flg": "",
			"permres_flg": "",
			"res_exp_code": "",
			"desc": "Imported edit"
		},
		{
			"census_flg": "N",
			"code": "TV",
			"expcode": "TEMPVISA",
			"citizen_flg": "",
			"permres_flg": "",
			"res_exp_code": "TEMPVISA",
			"desc": "Temporary Visa to allow assessment of Asylum claim"
		},
		{
			"census_flg": "N",
			"code": "TES",
			"expcode": "ABCFDS543534543",
			"citizen_flg": "",
			"permres_flg": "",
			"res_exp_code": "ABCFDS543534543",
			"desc": "Test Residency Status"
		},
		{
			"census_flg": "N",
			"code": "VIS",
			"expcode": "",
			"citizen_flg": "",
			"permres_flg": "",
			"res_exp_code": "",
			"desc": "Visa Students"
		}
	]
    ```
 
* **Error Response:**

    `codeonly` not supplied
    ```javascript
    "__msg": "'codeonly' IS REQUIRED"
    ```

    `codeonly` invalid
    ```javascript
    "__msg": "'codeonly' MUST BE 'true' or 'false'"
    ```
    
* **Sample Parameters:**

	```javascript
	codeonly=false
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	http://localhost/tassweb/api/?appcode=DEMOOE&v=1&method=GetResidencyStatuses&token=3w6XHPP1j163aHf%2FHRAnLA%3D%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://localhost/tassweb/api/">
		<input type="hidden" name="method" value="GetResidencyStatuses" />
		<input type="hidden" name="appcode" value="DEMOOE" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="1" />
		<textarea name="token">3w6XHPP1j163aHf\/HRAnLA==</textarea>
	</form>
	```