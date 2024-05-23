# bugHunt
- Web

## REPORTS - 
	- https://github.com/reddelexc/hackerone-reports
	- https://github.com/KathanP19/HowToHunt

## Checklist

### IDOR
	- IDOR in semrush academy [https://hackerone.com/reports/783708]
	
	- No error thrown when IDOR attempted while editing address[https://hackerone.com/reports/1085743]
	
	- IDOR when editing email leads to Account Takeover  [https://hackerone.com/reports/950881]
	
	- IDOR to view User Order Information [https://hackerone.com/reports/287789]
	
	- IDOR to account Takeover [https://hackerone.com/reports/1698006]
	
	- IDOR to Account Takeover [https://hackerone.com/reports/1952771]
	
	- IDOR on Program Visibilty [https://hackerone.com/reports/291721]
	
	- IDOR to Account Takeover [https://hackerone.com/reports/1272478]
	
	- IDOR to Reset Password [https://hackerone.com/reports/42587]
	
	- IDOR can delete animal from other account [https://hackerone.com/reports/1947376]
	
	- IDOR expire other user sessions [https://hackerone.com/reports/56511]
	
	- IDOR on upload profile functionality [https://hackerone.com/reports/741683]
	
### RESET PASS [check IDOR-Checklist.md]

### 2FA BYPASS, EMAIL BYPASS -
	- [https://github.com/KathanP19/HowToHunt/blob/master/Authentication_Bypass/2FA_Bypasses.md]
	- [https://github.com/reddelexc/hackerone-reports/blob/master/tops_by_bug_type/TOPMFA.md]
	
	- 2FA bypass by sending blank code [https://hackerone.com/reports/897385]
	
	- Enable 2FA without verifying the email [https://hackerone.com/reports/649533] [https://hackerone.com/reports/699200]
	
	- Password not checked when disabling 2FA [https://hackerone.com/reports/587910] 
	
	- Attacker has the email and password, the attacker can login in the account without the need of the 2fa code [https://hackerone.com/reports/665722]
	
	- Session Doesn't expire after 2fa and also other session can change passsword [https://hackerone.com/reports/2234736] [https://hackerone.com/reports/486693]
	
	- Able to blocking users with 2fa from login into their accounts by just knowing the SteamID [https://hackerone.com/reports/1179232]
	
	- Bypass two-factor authentication bruteforce [https://hackerone.com/reports/121696]
	


### Violation of secure design principle
	- Login page password-guessing attack [https://hackerone.com/reports/96115]
	
	- Account creation with invalid email addresses email is accepting % and %0d%0a [https://hackerone.com/reports/815085]
	
	- Improper Null Termination [https://hackerone.com/reports/2101076]
	
	- After changed pass usere didn't received any mail [https://hackerone.com/reports/38343]
	
	- Issue with remember_user_token [https://hackerone.com/reports/7931]
	
	- no verffication for changing email [https://hackerone.com/reports/546]
	
	- user can't recievied any mail if his accounts info are changed like country, email, payment method [https://hackerone.com/reports/961841]
	
	- Change payment method doesn't sent to the user email [https://hackerone.com/reports/240083]
	
### Disclosure of Secrets
### Improper Access Control
### Business Logic Errors
### * Account Takeover
### * Authentication Bypass
			
## Sensitive Data Exposure
- Disclosure of Secrets 
- Sensitive Token in URL
- Weak Password Reset Implementation -	[check IDOR-Checklist.md in Reset Password Section]
- EXIF Geolocation Data Not Stripped From Uploaded Images
- Visible Detailed Error/Debug Page

## Broken Authentication and Session 
- Failure to Invalidate Session
- Authentication Bypass
- Second Factor Authentication (2FA) Bypass
- Privilege Escalation
- Session Fixation - Remote Attack Vector
- Cleartext Transmission of Session Token
- Weak Login Function - Other Plaintext Protocol with no Secure Alternative
- Weak Login Function - 	Over HTTP
- Weak Registration Implementation - 	Over HTTP	

## Broken Access Control (BAC)
- Insecure Direct Object References (IDOR) [check IDOR-Checklist.md]
- Username/Email Enumeration - Non-Brute Force
- Exposed Sensitive Android Intent