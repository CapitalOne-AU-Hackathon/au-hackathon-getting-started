# API Usage

The following is examples of how to use and test the APIs 

## Table of Contents

### [API Calls](#api-calls)
### [Swagger] https://swaggerhub.com/apis/au_hackathon8 
### [Data Formatting for the APIs](#data-formatting-for-the-apis)

---

## API Calls

**There are 5 read only APIs: Transactions, Customers, Accounts, Rewards, Payments. There are 3 writable APIs: Update Customer, Add Account, Add Authorized User**

**List all accounts ids:**

POST https://3hkaob4gkc.execute-api.us-east-1.amazonaws.com/prod/au-hackathon/accounts

Body:
```
    {}
```

**List all customer ids:**

POST https://3hkaob4gkc.execute-api.us-east-1.amazonaws.com/prod/au-hackathon/customers

Body:               
```
    {}
``` 

**List account info:**

POST https://3hkaob4gkc.execute-api.us-east-1.amazonaws.com/prod/au-hackathon/accounts

Body:               
```
   {
       "account_id" : 100700000
   }
 ```
Sample Response:
```
[
    {
        "card_type": "VentureOne Rewards",
        "total_rewards_earned": 3330.5392500000003,
        "credit_limit": 266933.14,
        "account_id": 100700000,
        "total_rewards_used": 1732,
        "balance": 266443.14,
        "authorized_users": [
            {
                "customer_id": 100720000,
                "credit_card_number": "374622755572913"
            },
            {
                "customer_id": 100730000,
                "credit_card_number": "5100170539130426"
            },
            {
                "customer_id": 100740000,
                "credit_card_number": "3558996131935867"
            },
            {
                "customer_id": 100750000,
                "credit_card_number": "490555536224821533"
            },
            {
                "customer_id": 100760000,
                "credit_card_number": "5602257516580609"
            }
        ],
        "primary_user_card_number": "3583889085868805",
        "primary_user": 100710000
    }
]
 ```

**List customer info:**

POST https://3hkaob4gkc.execute-api.us-east-1.amazonaws.com/prod/au-hackathon/customers

Body:               
```
   {
       "customer_id" : 100720000
   }
 ```
Sample Response:
```
[
    {
        "customers": [
            {
                "last_name": "Bramwich",
                "gender": "Female",
                "first_name": "Farah",
                "customer_id": 100720000,
                "dob": "3/7/1966",
                "is_primary": false,
                "zipcode": "40546",
                "credit_card_number": "374622755572913",
                "is_married": false,
                "country": "United States",
                "email": "fbramwich1@wikimedia.org"
            }
        ],
        "account_id": 100700000
    }
]
 ```
 
 **List transaction info:**

POST https://3hkaob4gkc.execute-api.us-east-1.amazonaws.com/prod/au-hackathon/transactions

Body:               
```
   {
       "account_id" : 100700000
   }
 ```
Sample Response:
```
[
    {
        "customers": [
            {
                "customer_id": 100710000,
                "transactions": [
                    {
                        "transaction_row_id": 1,
                        "zipcode": "40618",
                        "month": "February",
                        "rewards_earned": 2.465,
                        "amount": 197.2,
                        "year": 2017,
                        "country": "United States",
                        "day": 24,
                        "transaction_id": 100710001,
                        "merchant_name": "baymont inn and suites ma"
                    },
                    {
                        "transaction_row_id": 2,
                        "zipcode": "90831",
                        "month": "May",
                        "rewards_earned": 2.76475,
                        "amount": 221.18,
                        "year": 2017,
                        "country": "United States",
                        "day": 22,
                        "transaction_id": 100710002,
                        "merchant_name": "c&c liquor commi"
                    },
                    
                                      ....
                    
                                      ....
                    
                                      ....
                    
                    {
                        "transaction_row_id": 343,
                        "zipcode": "60505",
                        "month": "February",
                        "rewards_earned": 2.841375,
                        "amount": 227.31,
                        "year": 2017,
                        "country": "United States",
                        "day": 14,
                        "transaction_id": 100760343,
                        "merchant_name": "wyoming game and fish dep"
                    },
                    {
                        "transaction_row_id": 344,
                        "zipcode": "33543",
                        "month": "May",
                        "rewards_earned": 1.043,
                        "amount": 83.44,
                        "year": 2017,
                        "country": "United States",
                        "day": 25,
                        "transaction_id": 100760344,
                        "merchant_name": "silverscript insurance"
                    }
                ]
            }
        ],
        "account_id": 100700000
    }
]
 ```
 
 **List rewards info:**

POST https://3hkaob4gkc.execute-api.us-east-1.amazonaws.com/prod/au-hackathon/rewards

Body:               
```
   {
       "account_id" : 100700000
   }
 ```
Sample Response:
```
[
    {
        "card_type": "VentureOne Rewards",
        "rewards": [
            {
                "month": "November",
                "total_rewards_earned": 240.96725,
                "total_rewards_used": 232,
                "rewards_remaining": 8.96725,
                "year": 2016
            },
            {
                "month": "December",
                "total_rewards_earned": 275.936625,
                "total_rewards_used": 275,
                "rewards_remaining": 9.903875,
                "year": 2016
            },
            {
                "month": "January",
                "total_rewards_earned": 296.336125,
                "total_rewards_used": 287,
                "rewards_remaining": 19.24,
                "year": 2017
            },
            {
                "month": "February",
                "total_rewards_earned": 320.839125,
                "total_rewards_used": 113,
                "rewards_remaining": 227.079125,
                "year": 2017
            },
            {
                "month": "March",
                "total_rewards_earned": 242.086,
                "total_rewards_used": 10,
                "rewards_remaining": 459.165125,
                "year": 2017
            },
            {
                "month": "April",
                "total_rewards_earned": 285.476,
                "total_rewards_used": 196,
                "rewards_remaining": 548.641125,
                "year": 2017
            },
            {
                "month": "May",
                "total_rewards_earned": 246.053125,
                "total_rewards_used": 25,
                "rewards_remaining": 769.69425,
                "year": 2017
            },
            {
                "month": "June",
                "total_rewards_earned": 292.270875,
                "total_rewards_used": 71,
                "rewards_remaining": 990.965125,
                "year": 2017
            },
            {
                "month": "July",
                "total_rewards_earned": 308.794125,
                "total_rewards_used": 112,
                "rewards_remaining": 1187.75925,
                "year": 2017
            },
            {
                "month": "August",
                "total_rewards_earned": 258.549875,
                "total_rewards_used": 52,
                "rewards_remaining": 1394.309125,
                "year": 2017
            },
            {
                "month": "September",
                "total_rewards_earned": 309.763875,
                "total_rewards_used": 179,
                "rewards_remaining": 1525.073,
                "year": 2017
            },
            {
                "month": "October",
                "total_rewards_earned": 253.46625,
                "total_rewards_used": 180,
                "rewards_remaining": 1598.53925,
                "year": 2017
            }
        ],
        "account_id": 100700000
    }
]
 ```

**List payment info:**

POST https://3hkaob4gkc.execute-api.us-east-1.amazonaws.com/prod/au-hackathon/payments

Body:               
```
   {
       "account_id" : 100700000
   }
 ```
Sample Response:
```
[
    {
        "card_type": "VentureOne Rewards",
        "account_id": 100700000,
        "payments": [
            {
                "total_monthly_balance": 19277.38,
                "year": 2016,
                "total_balance_remaining": 0,
                "total_balance_paid": 19277.38,
                "month": "November"
            },
            {
                "total_monthly_balance": 22074.93,
                "year": 2016,
                "total_balance_remaining": 0,
                "total_balance_paid": 22074.93,
                "month": "December"
            },
            {
                "total_monthly_balance": 23706.89,
                "year": 2017,
                "total_balance_remaining": 0,
                "total_balance_paid": 23706.89,
                "month": "January"
            },
            {
                "total_monthly_balance": 25667.13,
                "year": 2017,
                "total_balance_remaining": 0,
                "total_balance_paid": 25667.13,
                "month": "February"
            },
            {
                "total_monthly_balance": 19366.88,
                "year": 2017,
                "total_balance_remaining": 0,
                "total_balance_paid": 19366.88,
                "month": "March"
            },
            {
                "total_monthly_balance": 22838.08,
                "year": 2017,
                "total_balance_remaining": 0,
                "total_balance_paid": 22838.08,
                "month": "April"
            },
            {
                "total_monthly_balance": 19684.25,
                "year": 2017,
                "total_balance_remaining": 9207.25,
                "total_balance_paid": 10477,
                "month": "May"
            },
            {
                "total_monthly_balance": 32588.92,
                "year": 2017,
                "total_balance_remaining": 0,
                "total_balance_paid": 32588.92,
                "month": "June"
            },
            {
                "total_monthly_balance": 24703.53,
                "year": 2017,
                "total_balance_remaining": 0,
                "total_balance_paid": 24703.53,
                "month": "July"
            },
            {
                "total_monthly_balance": 20683.99,
                "year": 2017,
                "total_balance_remaining": 0,
                "total_balance_paid": 20683.99,
                "month": "August"
            },
            {
                "total_monthly_balance": 24781.11,
                "year": 2017,
                "total_balance_remaining": 22525.11,
                "total_balance_paid": 2256,
                "month": "September"
            },
            {
                "total_monthly_balance": 42802.41,
                "year": 2017,
                "total_balance_remaining": 0,
                "total_balance_paid": 42802.41,
                "month": "October"
            }
        ]
    }
]
 ```

**Add new account:**

Use this API to create a new sandbox account record. You can add authorized users (/add-au) for this sandbox account or modify customer (/update-customer) data.

POST https://3hkaob4gkc.execute-api.us-east-1.amazonaws.com/prod/au-hackathon/add-account

Body:
```
{
    "team_name" : required,
}
```

**Add authorized user**

Use this API to add authorized users to account records that belong to your team. Use the account id from your sandbox account and the same team_name for this account to create a new authorized user.

### Steps for adding a new authorized user ###
1. Create a new account using your team name 
2. Use the account id returned from creating an account to create the new authorized user
3. Transactions for the authorized user will **automatically** be added to the account

POST https://3hkaob4gkc.execute-api.us-east-1.amazonaws.com/prod/au-hackathon/add-au

Body:
```
{
    "team_name" : required,
    "account_id" : required 
}
```

**Update customer**

Use this API to update a customer record. The customer record must be part of the sandbox account with the same team_name as the request.

POST https://3hkaob4gkc.execute-api.us-east-1.amazonaws.com/prod/au-hackathon/update-customer

Body:
```
{
    "team_name" : required,
    "customer_id" : required,
    "first_name" : optional,
    "last_name" : optional,
    "address" : optional,
    "city" : optional,
    "state" : optional,
    "zipcode" : optional,
    "is_married" : optional,
    "phone_number" : optional,
    "email" : optional
}
```

**Full API Documentation is available on SwaggerHub**

---

## Swagger 
The Swagger files provide documentation on all of the APIs. Users can test the APIs directly using SwaggerHub

https://app.swaggerhub.com/apis/AU_HACKATHON8

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


#### Merchants list: https://s3.amazonaws.com/auhackathon-data/merchant_list.txt ####
#### Merchant codes: https://s3.amazonaws.com/auhackathon-data/MCC_Groups.xlsx ####
