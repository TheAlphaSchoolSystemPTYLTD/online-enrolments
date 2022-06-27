**getParentAddressSetup**
----
  Returns an array of all structured student medical note category setup details data in JSON format.
  
* **Version History:**

  TASS v57.8.100 - Method Added

* **Version:**

  3

* **Permission:**

  Parent Records > Parent Records Setup - Address tab - View

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
          "addr_desc":"Postal",
          "add_num":1,
          "person_posn":"",
          "posn_label":""
        },
        {
          "addr_desc":"Residential",
          "add_num":2,
          "person_posn":"",
          "posn_label":""
        }
      ],
      "__tassversion":"01.054.4.000",
      "token":{
        "timestamp":"{ts '2022-06-27 13:16:40'}"
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
    http://api.tasscloud.com.au/tassweb/api/?method=getParentAddressSetup&appcode=API04&company=10&v=3&token=l1D8owEn111IHcXLRwXTB0oU2GX6rj%2BISqa9zXA8We3J3mwgjW5pdUvFK3%2FIZ4mJ4bMyfKTmEoup%2B3tTE9GeLQ%3D%3D
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="getParentAddressSetup">
       <input type="hidden" name="appcode" value="API04">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="3">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We3J3mwgjW5pdUvFK3/IZ4mJ4bMyfKTmEoup+3tTE9GeLQ==</textarea>
    </form>
  ```