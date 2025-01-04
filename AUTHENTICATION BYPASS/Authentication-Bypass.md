## Authentication bypass via path manipulation
- if sensitive endpoint (ConfigUsers.aspx) redirect you to login page like Login.aspx, you can try
```
/ConfigUsers.aspx/Login.aspx  -> 200
/non-protected.aspx/protected.aspx
```

## Authentication bypass  via Improper Redirection Handling

- Using Burp Match And Replace or using Burp intercept response by :
```
	.>change 302 Moved Temporarily to 200 OK
	.>remove Location:/admin/Login.aspx?logout=y
	.>remove html redirect code
```

3. ==> Authentication bypass via cross-subdomain cookie reuse
	site:*.support.com
- When targeting a subdomain that operates on a third-party platform, investigate other customers using the same third-party service. If you discover functionalities available on these other subdomains—particularly those related to authentication or session management—test them on your target subdomain

If one subdomain allows user registration and the other doesn’t, register on the permissive subdomain and test whether its session cookies grant access on the restrictive subdomain. This can uncover critical cross-subdomain vulnerabilities.


4. ==>> Authentication bypass by Bypassing Registration Restrictions

- This example bears similarities to the previous bug we discussed, but it highlights another critical aspect we must consider
The E.G: (target.com)

	.> Using google dork `intext:"Copyright © 2023 target“` I discovered an application operating on a third-party platform, accessible via `target.Third-party.com`
	
	.> I encountered an endpoint, `target.Third-party.com/account/create/`, which appeared to be disabled, displaying only an empty page.“
	
	.> Using google dorks I found another customer use it (lets say for E.G bugcrowd) like bugcrowd.Third-party.com and `bugcrowd.Third-party.com/account/create` was working allowing me to reg
	
	.> Using the registration request from bugcrowd.Third-party.com/account/create, I modified the host in the request to target.Third-party.com/account/create using Burp Suite
	
	.> Since the process included email verification, I registered using my own email and received a verification email from target.Third-party.com. After verifying, I was able to log into target.Third-party.com
	


5. ==> URLScan.io: A Treasure for Hunters  Finding Auth Bypass Bugs

	.> Hidden endpoints that might expose vulnerabilities.
	
	.> Active password reset tokens that could lead to authentication bypasses
	
	.> Confirmation links that allow registration on subdomains not typically open to public registration

