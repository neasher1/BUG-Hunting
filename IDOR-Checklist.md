# IDOR Checklist

## User Profile:
- User photo deletion/editing via ID
- Editing/deleting user comments/posts/feedback via ID
- Changing profile information (name, email, etc.) with victim userID
- Viewing/editing other users private data (addresses, phone numbers) with userID manipulation
- reseting password/password change with victim userId 
- Viewing/ordering other users past purchases or orders by changing the order ID or user ID in URL parameters


## Authentication and Authorization:
- attacker able to expire other user session just changing the request with userId
- Accessing restricted pages or functionalities by changing user-specific tokens or IDs in URLs or request parameters
- Accessing premium content or features without proper authorization by manipulating user IDs or session tokens


## E-commerce Functionality:
- Modifying shopping cart contents or orders by changing the associated user ID or order ID
- Applying discounts or coupons intended for specific users by manipulating user IDs or coupon codes
- Viewing other users saved payment methods or addresses via ID manipulation


## Feedback and Reviews:
- Modifying or deleting reviews or feedback submitted by other users via direct object references in request parameters or URLs
- Submitting reviews or feedback on behalf of other users by manipulating user IDs or session tokens


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




## bypassing method
-----------------
GET /api_v1/messages?user_id=YOUR_USER_ID&user_id=ANOTHER_USERS_ID
GET /api_v1/messages?user_id=ANOTHER_USERS_ID&user_id=YOUR_USER_ID
GET /api_v1/messages?user_ids[]=YOUR_USER_ID&user_ids[]=ANOTHER_USERS_ID

## Change the request method
----------------------
try instead: GET, POST, PUT, DELETE, PATCH

## Change the requested file type
-------------
try adding .json