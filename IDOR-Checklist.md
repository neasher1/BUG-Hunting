# IDOR Checklist

## User Profile:
- User photo deletion/editing via ID
- Editing/deleting user comments/posts/feedback via ID
- Changing profile information (name, email, etc.) with victim userID
- Viewing/editing other users private data (addresses, phone numbers) with userID manipulation
    ### Reset Password
    - reseting password change with victim userId 
    - Full account takeover of any user through reset password: {"email":["victim@gmail.com","your@gmail.com"]} [https://hackerone.com/reports/1175081]
    - Password reset token leakage via referer [https://hackerone.com/reports/342693] [https://hackerone.com/reports/272379]
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
