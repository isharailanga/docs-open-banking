!!!note
    This document provides requests and responses for the sample Account Information Service API available in WSO2 Open 
    Banking Accelerator. 

- An API consumer can now invoke the `GET/ accounts/<ACCOUNT_ID>` endpoint. A sample request looks as follows:
```
curl -X GET \
https://localhost:8243/open-banking/v3.1/aisp/accounts/1' \
-H 'x-fapi-financial-id: open-bank' \
-H 'Authorization: Bearer <USER_ACCESS_TOKEN>' \
-H 'Accept: application/json' \
-H 'charset: UTF-8' \
-H 'Content-Type: application/json; charset=UTF-8'
--cert <PUBLIC_KEY_FILE_PATH> --key <PRIVATE_KEY_FILE_PATH> \
```
- The request retrieves the account information for the Account ID you mentioned in the request. A sample response looks 
as follows:
```
{
   "Data":{
      "Account":[
         {
            "AccountId":"1",
            "Status":"Enabled",
            "StatusUpdateDateTime":"2020-04-16T06:06:06+00:00",
            "Currency":"GBP",
            "AccountType":"Personal",
            "AccountSubType":"CurrentAccount",
            "Nickname":"Bills",
            "Account":[
               {
                  "SchemeName":"SortCodeAccountNumber",
                  "Identification":"1",
                  "Name":"Mr Kevin",
                  "SecondaryIdentification":"00021"
               }
            ]
         }
      ]
   },
   "Links":{
      "Self":"https://api.alphabank.com/open-banking/v3.0/accounts/1"
   },
   "Meta":{
      "TotalPages":1
   }
}
```