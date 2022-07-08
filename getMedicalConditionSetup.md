**getMedicalConditionSetup**
----
  Returns an array of structured student medical conditions setup details data in JSON format.
  
* **Version History:**

  TASS v57.8.100 - Method Added

* **Version:**

  3

* **Permission:**

  Medical Records > Medical Setup > Conditions tab > View

* **Method:**

  `GET | POST`
  
*  **Params:**

   **Required:**
 
   None

   **Optional:**

   None

   **Conditional:**

   None

* **Success Response:**

    ```javascript
    {
      "data":[
        {
          "mcud4_desc":"",
          "mcond_desc":"Accident",
          "mcud1_desc":"something",
          "mcud8_desc":"",
          "view_on_form_flg":"Y",
          "mcud3_desc":"",
          "mcud6_desc":"",
          "mcud10_desc":"",
          "mcond_alert_flg":"N",
          "mcud9_desc":"",
          "mcud5_desc":"",
          "active_flg":"Y",
          "mcond_code":"ACC",
          "mcud2_desc":"",
          "mcud7_desc":"",
          "parent_lounge_flg":"N"
        }
      ],
      "__tassversion":"01.054.4.000",
      "token":{
        "timestamp":"{ts '2022-06-24 13:00:40'}"
      }
    }
    ```

* **Error Response:**

    None
    
* **Sample Parameters:**

  ```javascript
    {}
  ```

* **Sample GET:** (With URL Encoded `token`)

  ```HTML
    http://api.tasscloud.com.au/tassweb/api/?method=getMedicalConditionSetup&appcode=API04&company=10&v=3&token=l1D8owEn111IHcXLRwXTB0oU2GX6rj%2BISqa9zXA8We3J3mwgjW5pdUvFK3%2FIZ4mJ4bMyfKTmEoup%2B3tTE9GeLQ%3D%3D
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="getMedicalConditionSetup">
       <input type="hidden" name="appcode" value="API04">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="3">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We3J3mwgjW5pdUvFK3/IZ4mJ4bMyfKTmEoup+3tTE9GeLQ==</textarea>
    </form>
  ```