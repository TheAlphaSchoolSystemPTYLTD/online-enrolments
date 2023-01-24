**getMedicalImmunisationSetup**
----
  Returns an array of all structured student medical immunisation setup details data in JSON format.
  
* **Version History:**

  TASS v57.8.100 - Method Added

* **Version:**

  3

* **Permission:**

  Medical Records > Medical Setup > Immunisations tab > View

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
      "data": [
        {
          "imm_desc": "Alcohol Ailment",
          "imm_code": "AA"
        },
        {
          "imm_desc": "Australian Flu",
          "imm_code": "AF"
        },
        {
          "imm_desc": "Bird Flu",
          "imm_code": "BF"
        },
        {
          "imm_desc": "Canadain Flu",
          "imm_code": "CF"
        },
        {
          "imm_desc": "Chicken Pox",
          "imm_code": "CP"
        },
        {...},
      ],
      "__tassversion": "01.057.8.100",
      "token": {
        "timestamp": "{ts '2023-01-24 14:44:19'}"
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
    http://api.tasscloud.com.au/tassweb/api/?method=getMedicalImmunisationSetup&appcode=API04&company=10&v=3&token=l1D8owEn111IHcXLRwXTB0oU2GX6rj%2BISqa9zXA8We3J3mwgjW5pdUvFK3%2FIZ4mJ4bMyfKTmEoup%2B3tTE9GeLQ%3D%3D
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="getMedicalImmunisationSetup">
       <input type="hidden" name="appcode" value="API04">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="3">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We3J3mwgjW5pdUvFK3/IZ4mJ4bMyfKTmEoup+3tTE9GeLQ==</textarea>
    </form>
  ```
