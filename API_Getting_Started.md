# API Usage

The following is examples of how to use and test the APIs 

## API Calls

**List all accounts:**

POST https://3hkaob4gkc.execute-api.us-east-1.amazonaws.com/prod/au-hackathon/accounts

Body:
```
    {
    
    }
```

**List all customer ids:**

POST https://3hkaob4gkc.execute-api.us-east-1.amazonaws.com/prod/au-hackathon/customers

Body:               
```
    {
    
    }
``` 

**List credit card numbers for an account:**

POST https://3hkaob4gkc.execute-api.us-east-1.amazonaws.com/prod/au-hackathon/accounts

Body:               
```
   {
   "account_id" : 100700000
   }
 ```

**Full API Documentation is available on SwaggerHub**

---
## Data Formatting for the APIs
The following is data limitations for the APIs

**Account ID, Customer ID or AU_ID, Transaction ID**
 
FORMAT : CCCCATTTT

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;CCCC= account_id
 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A= AU_ID/Customer ID

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TTTT = Transaction ID
 

Account_id : 1001 -3500

Customer ID / AU _ID   : 1-9  ( AU_ID = 1   is primary,   AU_ID = 2-9  means Authorized User.

Transaction id :  0001-0360

---
**Actual Range for Account_id = 100100000 – 350000000**

**Actual Range for AU_ID or Customer_ID =  100110000 - 350020000**

**Actual Range for transaction ID =  100110001  -   350020308**
 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;***Theoretical Range for Account_id = 100100000 – 350000000***

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;***Theoretical Range for AU_ID or Customer_ID =  100110000 - 350090000***

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;***Theoretical Range for transaction ID =  100110001  -   350099999***

---
**Merchant_Name** : 200+ merchant Names

**Transaction Date**: 11/1/2016   to 10/31/2017

**Rewards Month**: 11/2016 to 10/2017

**Payments Month**: 11/2016 to 10/2017
<br></br>
**Card Type:** "Venture Rewards","Quicksilver Rewards", "VentureOne Rewards", "Premier Dining Rewards", "Quicksilver One Rewards", "Platinum", "Journey Student Rewards", "Secured MasterCard","Spark Cash", "Spark Cash Select", "Spark Miles", "Spark Miles Select", "Spark Classic"
  <br></br>
**Person DOB** : 9/20/1960  to 9/20/1999
**IS_MARRIED** : TRUE or FALSE
**Transaction Amount** : $2.00  to $400  per transaction.
 <br></br>
**Rewards points are based on transaction amount:**

"Venture Rewards" = 2%

"Quicksilver Rewards" = 1.5%

"VentureOne Rewards" = 1.25%

"Savor" = 2%

"Quicksilver One Rewards" = 1.5%

"Platinum" = 0.5%

"Journey Student Rewards" = 1%

"Secured MasterCard" =.5%

"Spark Cash" = 2%

"Spark Cash Select" = 1.5%

"Spark Miles" = 2%

"Spark Miles Select" = 1.5%

"Spark Classic" = 1%

---

## Swagger 
The Swagger files provide documentation on all of the APIs. Users can test the APIs directly using SwaggerHub

https://app.swaggerhub.com/apis/AU_HACKATHON8

---

## Postman

### APIs (READ ONLY) Examples with Postman Endpoints ###

**TYPE: POST**

**BODY :- RAW**
<br></br>
**Customer**

https://3hkaob4gkc.execute-api.us-east-1.amazonaws.com/prod/au-hackathon/customers
```
{
    "customer_id" : 130010000
}
```
 
<br></br> 
**Transactions**

A list of all merchants: https://s3.amazonaws.com/auhackathon-data/merchant_list.txt

https://3hkaob4gkc.execute-api.us-east-1.amazonaws.com/prod/au-hackathon/transactions
```
{
    "card_number" : "502043092240039629",
    "date_from" : "11/1/2016"
}
```

<br></br> 
**Accounts**

https://3hkaob4gkc.execute-api.us-east-1.amazonaws.com/prod/au-hackathon/accounts
```
{
    "account_id" : 100300000
}
```
<br></br>
**Payments**

https://3hkaob4gkc.execute-api.us-east-1.amazonaws.com/prod/au-hackathon/payments
```
{
    "account_id" : 100200000
}
```
<br></br> 
**Rewards**

https://3hkaob4gkc.execute-api.us-east-1.amazonaws.com/prod/au-hackathon/rewards
```
{
    "account_id" : 100200000,
    "date_from" : "03/2017",
    "date_to" : "05/2017"
}
```
---

### API (POST) ###

**Add New Account**

https://3hkaob4gkc.execute-api.us-east-1.amazonaws.com/prod/au-hackathon/add_new_account
```
{
    "team_name" : required,
    "customer_id" : required 
}
```
<br></br>

**Add Authorized User**

https://3hkaob4gkc.execute-api.us-east-1.amazonaws.com/prod/au-hackathon/add_AU
```
{
    "team_name" : required,
    "customer_id" : required 
}
```
<br></br>
**Update Customer**

https://3hkaob4gkc.execute-api.us-east-1.amazonaws.com/prod/au-hackathon/update_customer
```
{
    "team_name" : required,
    "customer_id" : required 
}
```
