# bugHunt
- Web

## Checklist
- IDOR
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
	
- RESET PASS
- 2FA BYPASS, EMAIL BYPASS
- Violation of secure design principle
- Disclosure of Secrets
- Improper Access Control
- Business Logic Errors
-* Account Takeover
-* Authentication Bypass
			
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