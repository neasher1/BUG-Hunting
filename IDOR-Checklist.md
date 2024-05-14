# IDOR Checklist

## User Profile:
- User photo deletion/editing via ID
- Editing/deleting user comments/posts/feedback via ID
- Changing profile information (name, email, etc.) with victim userID
- Viewing/editing other users private data (addresses, phone numbers) with userID manipulation
    
    ### Reset Password [https://infosecwriteups.com/all-about-password-reset-vulnerabilities-3bba86ffedc7]

    - reseting password change with victim userId 

    - Password reset with manipulating email parameter: [https://hackerone.com/reports/1175081]
    ```
        JSON: {"email":["victim@gmail.com","your@gmail.com"]} 

        Double parameter: email=victim@xyz.tld&email=hacker@xyz.tld

        carbon copy: email=victim@xyz.tld%0a%0dcc:hacker@xyz.tld
        
        Using separators: email=victim@xyz.tld,hacker@xyz.tld
                        email=victim@xyz.tld%20hacker@xyz.tld
                        email=victim@xyz.tld|hacker@xyz.tld
    ```
    

    - Password reset token leakage via Referer Header [https://hackerone.com/reports/342693] [https://hackerone.com/reports/272379]

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


- Viewing/ordering other users past purchases or orders by changing the order ID or user ID in URL parameters


## Authentication and Authorization:
- attacker able to expire other user session just changing the request with userId
- Accessing restricted pages or functionalities by changing user-specific tokens or IDs in URLs or request parameters
- Accessing premium content or features without proper authorization by manipulating user IDs or session tokens


## E-commerce Functionality:
- Modifying shopping cart contents or orders by changing the associated user ID or order ID
- Applying discounts or coupons intended for specific users by manipulating user IDs or coupon codes
- Viewing other users saved payment methods or addresses via ID manipulation

    ### Product Management:
    - Adding/removing products to/from the shopping cart by manipulating product IDs or quantities in requests
    - Changing product details (such as name, description, price) via direct object references in URLs or request parameters
    - Accessing unpublished or hidden products by guessing or manipulating product IDs in URLs

    ### Order Management:
    - Viewing/modifying order details (items, shipping address, payment method) by changing order IDs in URLs or request parameters
    - Cancelling or refunding orders placed by other users by manipulating order IDs or user IDs
    - Accessing order history or invoices of other users by guessing or manipulating user IDs in URLs

    ### Payment Processing:
    - Making purchases with stolen credit card information by manipulating payment token IDs or transaction IDs
    - Accessing payment confirmation pages or receipts of other users by changing order IDs or user IDs in URLs
    - Modifying payment amounts or currency conversion rates in payment requests via ID manipulation

    ### Discounts and Coupons:
    - Applying discounts or coupons intended for specific users by manipulating user IDs or coupon codes
    - Bypassing coupon code validation checks to redeem expired or one-time-use coupons by manipulating coupon IDs or codes
    - Accessing discount codes or promotional offers of other users by guessing or manipulating user IDs in URLs

    ### Shipping and Delivery:
    - Viewing/modifying shipping details (carrier, tracking number, delivery address) by changing order IDs in URLs or request parameters
    - Redirecting shipments to different addresses or intercepting deliveries by manipulating order IDs or shipping IDs
    - Accessing shipping labels or delivery status of other users by guessing or manipulating user IDs in URLs

    ### Customer Support:
    - Accessing customer support tickets or inquiries submitted by other users by guessing or manipulating ticket IDs or user IDs
    - Modifying or deleting customer support tickets or messages via direct object references in request parameters or URLs
    - Responding to customer support inquiries on behalf of other users by manipulating user IDs or session tokens

    ### Product Reviews and Ratings:
    - Modifying or deleting product reviews or ratings submitted by other users via direct object references in request parameters or URLs
    - Submitting reviews or ratings on behalf of other users by manipulating user IDs or session tokens
    - Accessing product review analytics or insights of other users by guessing or manipulating user IDs in URLs

    ### Wishlist and Favorites:
    - Accessing or modifying items in other users wishlists or favorites lists by changing user IDs or session tokens in URLs or request parameters
    - Adding or removing items from other users wishlists or favorites lists via ID manipulation
    



## Messaging/Chat Systems:
- Viewing/modifying other users messages or chat history by manipulating message IDs or user IDs in API requests
- Accessing private conversations or group chats by guessing or manipulating conversation IDs
- Deleting/editing messages or chat history via ID manipulation


## File and Resource Access:
- Accessing private files or documents by guessing or manipulating file IDs or URLs
- Viewing/editing sensitive documents or images via direct object references in URL parameters
- Accessing restricted media content (videos, images) by changing media IDs or session tokens in URLs


## User Permissions and Roles:
- Elevating privileges by manipulating user roles or permissions via ID manipulation
- Accessing administrative functionalities or dashboards by changing user roles or IDs in request parameters


## Financial Transactions:
- Viewing/modifying other users financial transactions or payment history by manipulating transaction IDs or user IDs
- Accessing sensitive financial information or transaction details via direct object references in URLs or request parameters


## Third-party Integrations:
- Accessing or modifying data from integrated services (social media, payment gateways) by manipulating IDs or tokens passed in API requests

----------------------------------------------------------------    
----------------------------------------------------------------
