### Reset Password 
[All About Password Reset Vulnerability] (https://infosecwriteups.com/all-about-password-reset-vulnerabilities-3bba86ffedc7)
    
(https://anugrahsr.github.io/posts/10-Password-reset-flaws/#10-try-using-your-token)

- reseting password change with victim userId 

- Password reset with manipulating email parameter: [https://hackerone.com/reports/1175081]
    ```
        JSON: {"email":["victim@gmail.com","your@gmail.com"]} 

        Double parameter: email=victim@xyz.tld&email=hacker@xyz.tld

        carbon copy: email=victim@xyz.tld%0a%0dcc:hacker@xyz.tld
                     email="victim@mail.tld%0a%0dbcc:attacker@mail.tld"

        Using separators: email=victim@xyz.tld,hacker@xyz.tld
                        email=victim@xyz.tld%20hacker@xyz.tld
                        email=victim@xyz.tld|hacker@xyz.tld
    ```
    

    - Password reset token leakage via Referer Header [272379] (https://hackerone.com/reports/342693) [272379](https://hackerone.com/reports/272379)

    - Password Reset link hijacking via Host Header Poisoning [https://hackerone.com/reports/226659] [https://www.skeletonscribe.net/2013/05/practical-http-host-header-attacks.html]   [https://medium.com/@tameemkhalid/host-header-injection-on-password-reset-functionality-an-easy-p2-5c6263c2e3d4]

    ```
        Host: attacker.com

        Host: target.com
        X-Forwarded-Host: attacker.com

        Host: target.com
        Host: attacker.com
    ```

    - Password Reset By Manipulating Email Parameter [https://medium.com/@0xankush/readme-com-account-takeover-bugbounty-fulldisclosure-a36ddbe915be]

    - Changing Email And Password of any User through API Parameters [https://ad3sh.medium.com/full-account-takeover-changing-email-and-password-of-any-user-through-api-parameters-3d527ab27240]

    - Forgot password link doesn't expire after used [https://hackerone.com/reports/244642]

    - Reset password link sent over unsecured http protocol [https://hackerone.com/reports/1888915]

    - User enumeration via Password reset page [https://hackerone.com/reports/1166054] [https://hackerone.com/reports/77067]

    - Logout CSRF [https://hackerone.com/reports/223329]

    - Activation tokens are not expiring [https://hackerone.com/reports/223339]

    - Design Flaw in session management of password reset [https://hackerone.com/reports/229417]

    - weak cryptography issue [https://infosecwriteups.com/bugbounty-how-i-was-able-to-compromise-any-user-account-via-reset-password-functionality-a11bb5f863b3]

    - Response Manipulation: Replace Bad Response With Good One [https://medium.com/@innocenthacker/how-i-found-the-most-critical-bug-in-live-bug-bounty-event-7a88b3aa97b3]

    -Failure to Invalid Session after Password Change [https://hackerone.com/reports/514577] [https://hackerone.com/reports/678050]