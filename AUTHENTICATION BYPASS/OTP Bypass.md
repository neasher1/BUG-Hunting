# OTP Bypass on Register account via Response manipulation 

## First Method
- Register account with mobile number and request for OTP.
- Enter incorrect OTP and capture the request in Burpsuite.
- Do intercept response to this request and forward the request.
- response will be
``` {"verificationStatus":false,"mobile":9072346577","profileId":"84673832"} ```
- Change this response to
``` {"verificationStatus":true,"mobile":9072346577","profileId":"84673832"} ```
- And forward the response.
- You will be logged in to the account.
Impact: Account Takeover


## Second Method:
```    
    1.Register 2 accounts with any 2 mobile number(first enter right otp)
    2.Intercept your request
    3.click on action -> Do intercept -> intercept response to this request.
    4.check what the message will display like status:1
    5.Follow the same procedure with other account but this time enter wrong otp
    6.Intercept respone to the request
    7.See the message like you get status:0
    8.Change status to 1 i.e, status:1 and forward the request if you logged in means you just done authentication bypass. 
```

## Bypassing OTP in registration forms by repeating the form submission multiple times using repeater
```
    1. Create an account with a non-existing phone number
    2. Intercept the Request in BurpSuite
    3. Send the request to the repeater and forward
    4. Go to Repeater tab and change the non-existent phone number to your phone number
    5. If you got an OTP to your phone, try using that OTP to register that non-existent number
```

## No Rate Limit
```
    1) Create an Account
    2) When Application Ask you For the OTP( One-time password ), Enter wrong OTP and Capture this Request In Burp.
    3) Send This Request into Repeater and repeat it by setting up payload on otp Value.
    4) if there is no Rate Limit then wait for 200 Status Code (Sometimes 302)
    5)if you get 200 ok or 302 Found Status Code that means you've bypass OTP
```

## More test cases for bypassing OTP-
```
    1) Check for default OTP - 111111, 123456, 000000
    2) Check if otp has been leaked in respone (Capture the request in burpsuite and send it to repeater to check the response)
    3) Check if old OTP is still vaild
```