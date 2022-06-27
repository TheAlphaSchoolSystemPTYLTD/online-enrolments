**getStudentMedicalUDSetup**
----
  Returns an array of all structured student medical UD setup details data in JSON format.
  
* **Version History:**

  TASS v57.8.100 - Method Added

* **Version:**

  3

* **Permission:**

  Medical Records > Medical Setup > Initialise User Defined Fields (UD) > View

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
      "__tassversion":"01.054.4.000",
      "token":{
        "includelookups":true,
        "timestamp":"{ts '2022-06-24 13:06:10'}"
      },
      "ud":[
        {
          "flag_name":"MUD1_FLG",
          "id":1,
          "desc":"Diabeties",
          "name":"UD1_DESC"
        },...
        {
          "flag_name":"MUD1_CODE",
          "id":6,
          "lookups":[
            {
              "code":"MA",
              "desc":"Mater"
            },
            {
              "code":"PC",
              "desc":"Prince Charles"
            },
            {
              "code":"RBH",
              "desc":"Royal Brisbane"
            },
            {
              "code":"WE",
              "desc":"Wesley"
            }
          ],
          "desc":"Preferred Hospital",
          "name":"UD6_DESC"
        }
      ]
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
    http://api.tasscloud.com.au/tassweb/api/?method=getStudentMedicalUDSetup&appcode=API04&company=10&v=3&token=l1D8owEn111IHcXLRwXTB0oU2GX6rj%2BISqa9zXA8We3J3mwgjW5pdUvFK3%2FIZ4mJ4bMyfKTmEoup%2B3tTE9GeLQ%3D%3D
  ```
  
* **Sample POST:**

  ```HTML
    <form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
       <input type="hidden" name="method" value="getStudentMedicalUDSetup">
       <input type="hidden" name="appcode" value="API04">
       <input type="hidden" name="company" value="10">
       <input type="hidden" name="v" value="3">
       <textarea name="token">l1D8owEn111IHcXLRwXTB0oU2GX6rj+ISqa9zXA8We3J3mwgjW5pdUvFK3/IZ4mJ4bMyfKTmEoup+3tTE9GeLQ==</textarea>
    </form>
  ```