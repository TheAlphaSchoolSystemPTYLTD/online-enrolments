**getMedicalNoteCategorySetup**
----
  Returns an array of all structured student note category setup details data in JSON format.
  
* **Version History:**

  TASS v57.8.100 - Method Added

* **Version:**

  3

* **Permission:**

  Medical Records > Medical Setup > Note Categories tab > View

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
          "ncat_desc":"Doctor Advice",
          "note_cat":"DOC"
        },
        {
          "ncat_desc":"General",
          "note_cat":"GEN"
        }
      ],
      "__tassversion":"01.054.4.000",
      "token":{
        "timestamp":"{ts '2022-06-24 13:04:20'}"
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
    http://api.tasscloud.com.au/tassweb/api/?method=getMedicalNoteCategorySetup&appcode=API04&company=10&v=3&token=l1D8owEn111IHcXLRwXTB0oU2GX6rj%2BISqa9zXA8We3J3mwgjW5pdUvFK3%2FIZ4mJ4bMyfKTmEoup%2B3tTE9GeLQ%3D%3D
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="getMedicalNoteCategorySetup">
       <input type="hidden" name="appcode" value="API04">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="3">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We3J3mwgjW5pdUvFK3/IZ4mJ4bMyfKTmEoup+3tTE9GeLQ==</textarea>
    </form>
  ```