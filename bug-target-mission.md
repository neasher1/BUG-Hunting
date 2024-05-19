# bugHunt
- Web
			
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