# Feature: My Account Page

---

# User Story

As a logged-in user,  
I want to access my "My Account" page,  
So that I can manage my personal information, orders, and account settings.

Priority: High  
Type: Functional  

---

# AC - My Account Page Structure

Given the user is logged in  
When the user clicks on the "My Account" button  
Then the user is redirected to the My Account page  
And the page displays a side navigation list containing:

- Customer Info
- Addresses
- Orders
- Recurring Payments
- Downloadable Products
- Back in Stock Subscriptions
- Reward Points
- Change Password
- My Product Reviews

And:
- The URL reflects the My Account page
- Page loads without errors

---

# AC - Access Control

Given the user is NOT logged in  
When the user tries to access the My Account URL directly  
Then the system redirects the user to the Login page  

---

# AC - Active Element State

Given the user is on the My Account page  
When the user selects an item from the side list  
Then:
- The main content area updates accordingly
- The selected item is visually highlighted
- The page title matches the selected section
- The URL updates to reflect the selected section
- Refreshing the page keeps the same section active

---

# AC - Customer Info Structure

Given the user selects "Customer Info"  
When the page loads  
Then the user sees:

## Personal Details
- Gender
- First Name (Required)
- Last Name (Required)
- Email (Required)

## Company Details
- Company Name (Optional)

## Newsletter
- Subscribe checkbox (Optional)

And:
- Save button is visible and enabled

---

# AC - Customer Info Core

Given the user enters valid data in required fields  
When the user clicks Save  
Then:
- Data is updated successfully
- Success message appears
- Updated email (if changed) can be used to log in

---

# AC - Customer Info Validation

Given the user leaves a required field empty  
When the user clicks Save  
Then:
- Validation message appears near the field
- Focus moves to the first invalid field
- Data is not saved

---

# AC - Customer Info (No Changes)

Given the user submits the same existing data  
When the user clicks Save  
Then:
- Informational message appears (e.g., "No changes were made")
- No system crash occurs

---

# AC - Addresses (No Existing Address)

Given the user navigates to Addresses  
When no addresses are saved  
Then:
- Empty state message appears
- "Add New Address" button is visible

---

# AC - Add New Address Structure

Given the user clicks "Add New Address"  
When the page loads  
Then the following fields are displayed:

- First Name (Required)
- Last Name (Required)
- Email (Required)
- Company
- Country (Required)
- State/Province
- City (Required)
- Address 1 (Required)
- Address 2
- Zip/Postal Code (Required)
- Phone Number (Required)
- Fax Number
- Save button

---

# AC - Add Address Core

Given the user fills required fields correctly  
When the user clicks Save  
Then:
- Address is saved
- Success message appears
- Address appears in address list
- Address becomes selectable during checkout

---

# AC - Edit Address

Given the user edits an existing address  
When the user clicks Save  
Then:
- Address is updated
- Updated data appears correctly in list

---

# AC - Delete Address

Given the user clicks Delete  
When the user confirms deletion  
Then:
- Address is removed from list
- No system crash occurs

---

# AC - Address Validation

Given required field is empty  
When Save is clicked  
Then:
- Validation message appears
- Address is not saved

---

# AC - Orders Section

Given the user navigates to Orders  
When the page loads  
Then:
- Order Number is displayed
- Order Status is displayed
- Order Date is displayed
- View Details button is available

If no orders exist:
- Empty state message appears

---

# AC - Orders Status Logic

Given an order is cancelled  
When user views Orders  
Then:
- Order remains visible
- Status shows "Cancelled"

Cancelled orders:
- Do NOT grant reward points

---

# AC - Orders Details

Given the user has a checked-out order 
When the user click on the order details 
Then the user will be redirected to the order details page
And the user will be able to monitor and control his orders

---

# AC - Reward Points

Given the user navigates to Reward Points  
When page loads  
Then:
- Total accumulated points are displayed
- History of earned points is displayed (if available)

## Business Logic:
- Every $10 = 1 point
- Integer division only
  - $139 → 13 points
  - $19 → 1 point
- Cancelled orders do not generate points

---

# AC - Recurring Payments

Given the user has recurring payments  
When navigating to section  
Then:
- All recurring payments are listed
- Each shows current status

---

# AC - Downloadable Products

Given the user navigates to Downloadable Products  
When page loads  
Then:
- Purchased downloadable products are listed
- Download link is visible for eligible items

---

# AC - Back in Stock Subscriptions

Given the user navigates to Back in Stock Subscriptions  
When page loads  
Then:
- All subscribed products are listed

---

# AC - Change Password Structure

Given the user navigates to Change Password  
When page loads  
Then:
- Old Password (Required)
- New Password (Required, minimum 6 characters)
- Confirm Password (Required)
- Change Password button
- Forgot Password link

---

# AC - Change Password Core

Given:
- Old password is correct
- New password ≥ 6 characters
- Confirm password matches

When user clicks Change Password  
Then:
- Password is updated
- Success message appears
- User can log in with new password

---

# AC - Change Password Validation

Given any required field is empty  
When user clicks Change Password  
Then:
- Validation message appears
- Password is not updated

Given Old Password is incorrect  
Then:
- Error message appears
- Password is not updated

Given New Password = Old Password  
Then:
- Validation message appears
- Focus moves to New Password field

---

# Customer Info - Core functional

| TC ID | Title | Priority | Preconditions | Steps | Expected Results | 
| --- | --- | --- | --- | --- | --- |
| **CUSINFO-Fun-01** | Validate updating any field in the customer info's | High | Customer info fields loaded | 1. Edit the data of the required field <br> 2. Click on the save button | 1. Data is updated successfully <br> 2. Success change info message: (The customer info has been updated successfully.) <br> 3. The system placed the new data inside the fields <br> user is allowed to  log in using the new data |
| **CUSINFO-Fun-02** | Validate no cange made o customer info | low | Customer info fields loaded | 1. Keep the same old data without modifications <br> 2. Click on the save button | 1. Data is updated successfully <br> 2. Success change info message: (The customer info has been updated successfully.) |
--- 

# Customer Info - Validation

| TC ID | Title | Priority | Preconditions | Steps | Expected Results | 
| --- | --- | --- | --- | --- | --- |
| **CUSINFO-Val-01** | Validate leaving a mandatory field empty | Medium | Customer info fields loaded | 1. Erase any mandatory field data <br> 2. Click on the " Save " button | 1. Request is rejected <br> 2. A validation error message appears near the empty required field | 
| **CUSINFO-Val-02** | Validate using a wrong format email | High | Customer info fields loaded | 1. Fill the email field with a wrong format email (saas@asas) <br> 2. Click on the " Save " button | 1. Request is rejected <br> 2. A validation error message appears indicating that (Wrong Email) is used | 
| **CUSINFO-Val-03** | Validate leaving a required field empty | High | Customer info fields loaded | 1. Leave only one mandatory field empty <br> 2. Fill the rest mandatory fields with valid data <br> 3. Click on the " Save " button <br> 4. Repeat these steps for every field | 1. Request is rejected <br> 2. A validation error message appears near the empty mandatory| field
---

# Customer Info - Edge

| TC ID | Title | Priority | Preconditions | Steps | Expected Results | 
| --- | --- | --- | --- | --- | --- |
| **CUSINFO-Edge-01** | Validate spam click on the save button | Low | User is on the customer info page | Click for a multiple times on the save button | 1. Each click is handled separately <br> 2. Success save message for each click <br> 3. No Crash |
| **CUSINFO-Edge-02** | Validate refresh the page after saving | Low | Customer saved the new modifications | 1. Refresh the page <br> 2. Observe all the field's content | 1. The fields show the latest updated data |

---

# Customer Info - Security

| TC ID | Title | Priority | Preconditions | Steps | Expected Results | 
| --- | --- | --- | --- | --- | --- |
| **CUSINFO-Sec-01** | Validate and replace the old email with the already registered email | High | Customer info fields loaded | 1. Replace the old email with another registered email <br> 2. Click on the save button | 1. Validation error message indicating: (This email is linked to another account.) | 
| **CUSINFO-Sec-02** | Validate using SQL code inside the email field | High | Customer info fields loaded | 1. Enter inside the email field --> OR '1'='1' <br> 2. Click on the save | 1. Wrong email validation message <br> 2. The system does not execute the code <br> 3. No sensitive data is shown |
| **CUSINFO-Sec-03** | Validate using a script inside the name fields | High | Customer info fields loaded | 1. Fill the first name field with JavaScript code <br> 2. Click on the Save button | 1. The code is not executed <br> 2. No crash <br> 3. No unusual activity (popups......)

---

# Customer Info - API 

| TC ID | Title | Priority | Preconditions | Steps | Expected Results | 
| --- | --- | --- | --- | --- | --- |
| **CUSINFO-API-01** | Validate changing customer info status code | Medium | User is on Postman | Create a put request | Response code equals (200) |
| **CUSINFO-API-02** | Validate changing customer info response time | Medium | User is on Postman | Create a put request | Response time must not exceed 300ms | 

> Response time based on best practices and UX performance standards

---

# Address - Core Functional 

| TC ID | Title | Priority | Preconditions | Steps | Expected Results | 
| --- | --- | --- | --- | --- | --- |
| **ADDRESS-FUN-01** | Validate adding a new address | High | My account page loaded | 1. Click on the Address | 1. Click on the " Add New " button <br> 2. Fill all of the mandatory fields <br> 3. Click on the " Save " button | 1. Success operation message <br> 2. The system will preview the address information <br> 3. The system allows the user to manage the added address (Edit/Delete) | 
| **ADDRESS-FUN-02** | Validate Editing an Address | High | user has a saved Address | 1. Click on the Edit button <br> 2. Edit any field <br> 3. Click on the " Save " button | 1.  1. Success operation message <br> 2. The system shows the new updated data | 

--- 

# Address - Validation 

| TC ID | Title | Priority | Preconditions | Steps | Expected Results | 
| --- | --- | --- | --- | --- | --- |
| **ADDRESS-VAL-01** | Validate Adding/Editing Address and leaving required fields empty | High | Address fields loaded | 1. Leave all the required fields empty <br> 2. Click on the " Save " button | 1. Validation error message indicating " ____ field is required | for each missing required field | 
| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| **ADDRESS-VAL-02** | Validate Invalid email format | High | Address fields loaded | Enter wrong email → save | Email validation error shown |
| **ADDRESS-VAL-03** | Validate Spaces-only input | Medium | Address fields loaded | Enter spaces in required fields | Field rejected and error displayed |
| **ADDRESS-VAL-04** | Validate Missing mandatory field | High | Address fields loaded | Leave one required field empty | Form blocked and specific error shown |

---

# Address - Edge 

| TC ID | Title | Priority | Preconditions | Steps | Expected Results | 
| --- | --- | --- | --- | --- | --- |
| **ADDRESS-ED-01** | Validate adding mulltiple Addresses | Low | User is on the Address screen | 1. Click on the Add New button <br> 2. Fill all mandatory fields <br> 3. Click on the save button <br> 4. Repeat the previous steps for many times | 1. The system saves each address separately <br> 2. The new address won't replace the old address |
| **ADDRESS-ED-02** | Validate repeated clicking clicking of the " Save " button| Low | Address fields loaded | 1. Fill all mandatory fields with valid data <br> 2. Click the "Save " button repeatedly within a short time | 1. System saves and previews one address | 
| **ADDRESS-ED-03** | Verify refreshing the page after adding/editing an address | Medium | New/Edited address is saved | 1. Refresh the page | 1. The Added Address still exists and shows the right data <br> 2. The Edited Address shows the latest edited version | 
| **ADDRESS-ED-04** | Validate using space between email characters | Medium | Address fields loaded | 1. Fill the email field with leading/trailing space <br> 2. Fill all mandatory fields <br> 3. Click on the " Save " button | System handles correctly with the space |
| **ADDRESS-ED-05** | Validate copy and paste data to the address fields | Low | User has access to external note app, Address fields loaded | 1. Open the note app <br> 2. Type the data <br> 3. Copy the data <br> 4. Navigate to the Address page <br> 5. Paste the data | System accepts the inputs |

---

# Address - Integration

| TC ID | Title | Priority | Preconditions | Steps | Expected Results | 
| --- | --- | --- | --- | --- | --- |
| **ADDRESS-ED-01** | Validate saved address available to the user to select when checking out | Medium | User is on the checkout page | 1. Observe the available addresses for the billing & shipping addresses | The system shows all addresses, and the user is allowed to select one of them | 


---

# Address - Security 

| TC ID | Title | Priority | Preconditions | Steps | Expected Results | 
| --- | --- | --- | --- | --- | --- |
| **ADDRESS-SEC-01** | Validate using SQL code inside the address fields | High | Address fields loaded | 1. Enter a SQL code <br> 2. Click on the " Save " button | 1. System will not execute the code <br> 2. No sensitive data displayed <br> 3. No Crash |
| **ADDRESS-SEC-02** | Validate using JavaScript code inside the address fields | High | Address fields loaded | 1. Enter a SQL code <br> 2. Click on the " Save " button | 1. System will not execute the code <br> 2. No sensitive data displayed <br> 3. No Crash |

---

# Adress - API 

| TC ID | Title | Priority | Preconditions | Steps | Expected Results | 
| --- | --- | --- | --- | --- | --- |
| **ADDRESS-API-01** | Validate adding address status code | Medium | User is on Postman | Create a post request | Status code equals (200) | 
| **ADDRESS-API-02** | Validate changing Address status code | Medium | User is on Postman | Create a put request | Status code equals (200) |
| **ADDRESS-API-03** | Validate changing Address response time | Medium | User is on Postman | Create a put request | Response time must not exceed 300ms | 
| **ADDRESS-API-04** | Validate Adding Address response time | Medium | User is on Postman | Create a post request | Response time must not exceed 300ms | 
| **ADDRESS-API-05** | Validate the status code for with a mistake in the address field | Medium | User is on Postman | Create a request | Status code equals (400) Bad request | 

> Response time based on best practices and UX performance standards


# Orders - Core functional

| TC ID | Title | Priority | Preconditions | Steps | Expected Results | 
| --- | --- | --- | --- | --- | --- |
| **ORDERS-FUN-01** | Validate that all checked-out orders appear | High | User completed two orders | 1. Navigate to my account page <br> 2. Selet " Order " from the side list | All checked-out orders appear | 
| **ORDERS-FUN-02** | Validate navigating to the order details page | High | User is on the " Orders " screen | Clicks on the Details link for any order & has checked-out rders | System redirects the user to the order details page | 
| **ORDERS-FUN-03** | Validate Order date filter functionality | Medium | User is on the " Orders " screen & has checked-out orders | 1. Click on the filter drop-down menu list <br> 2. Select the desired period | System previews only the orders matching the selected period of time | 

---

# Orders - EDGE

| TC ID | Title | Priority | Preconditions | Steps | Expected Results | 
| --- | --- | --- | --- | --- | --- |
| **ORDERS-ED-01** | Validate using the browser back button to reset filter | Low | User is on the " Orders " screen & has checked-out orders | 1. Select a date filter <br> 2. Click on the " Browsers Back Button." | The system returns the user to the state before the selected filter | 
| **ORDERS-ED-02** | Validate the system shows the cancelled orders | low | User canceled an order | 1. Navigate to the " My account page " <br> 2. Click on the " Orders " from the side list <br> 3. Look for the canceled order | 1. The user sees the order <br> 2. Order status is canceled |
---

# Orders - UI

| TC ID | Title | Priority | Preconditions | Steps | Expected Results | 
| --- | --- | --- | --- | --- | --- |
| **ORDERS-UI-01** | Verify orders data is not mixed or overlapping in UI | Medium | User has checked-out orders & Orders screen loaded | Check each order data | System shows the orders separately with their correct data without overlapping |

---

# Recurring payments - Core Functional

| TC ID | Title | Priority | Preconditions | Steps | Expected Results | 
| --- | --- | --- | --- | --- | --- |
| **RECPAY-FUN-01** | Validate the system shows the recurring payments | Medium | User has a recurring payment | 1. Navigate to my account page <br> 2. Select recurring payments | System will show all recurring payments the user has | 

---

# Back in stock subscriptions - Core Functional

| TC ID | Title | Priority | Preconditions | Steps | Expected Results | 
| --- | --- | --- | --- | --- | --- | 
| **BKNSTK-FUN-01** | Validate all Back in stock products subscription appear | low | User subscribed to a back in stock reminder for a product | 1. Navigate to my account page <br> 2. Select Back in stock subscriptions | System will show all Back in stock subscriptions the user has | 

---

# Rewards points - Core functional 

| TC ID | Title | Priority | Preconditions | Steps | Expected Results | 
| --- | --- | --- | --- | --- | --- | 
| **REWARDSPT-Fun-01** | Validate the system shows the user's rewards points | Low | User completed order with price not less than 10$ | 1. Navigate to the my account page <br> 2. Click on the rewards points | The system shows the correct total rewards points | 

---

# Rewards points - Security

| TC ID | Title | Priority | Preconditions | Steps | Expected Results | 
| --- | --- | --- | --- | --- | --- | 
| **REWARDSPT-SEC-01** | Validate the rewards points when canceling an order | High | User Canceled order | 1. Navigate to the my account page <br> 2. Clickon the Rewards points from the side list | System handles the cancellation correctly |

---

 **Password constraints:**
   - At least six characters
     
# Change Password - Core Functional

| TC ID | Title | Priority | Preconditions | Steps | Expected Results | 
| --- | --- | --- | --- | --- | --- | 
| **PASS-Fun-01** | Validate changing the password | High | Change password screen loaded | 1. Fill the old password field <br> 2. Enter a Valid password inside the new password field <br> 3. Fill the confirm password field with the same new password <br> 4. Click on the " Change Password " button | System confirms and accepts operation |
| **PASS-Fun-02**| Validate the user resets his password if he forgets his old password | High |  Change password screen loaded | 1. Click on the forgot password <br> 2. Fill the email field | The system will send a reset password email, and the user will be able to reset his password | 

---

# Change Password - Validation

| TC ID | Title | Priority | Preconditions | Steps | Expected Results | 
| --- | --- | --- | --- | --- | --- | 
| **PASS-Val-01** | Validate leaving all fields empty | High | Change password screen loaded | 1. Leave all fields empty <br> 2. Click on the " Change Password " button. | 1. The system rejects the request <br> 2. Validation error message near all mandatory fields |
| **PASS-Val-02** | Validate leaving the old password field empty | Low | Change password screen loaded | 1. Leave the " Old password " field empty <br> 2. Fill in the new password and the confirmation password with the same valid password. <br> 3. Click on the " Change password " field | System rejects the request, and a Validation error message appears near the old password field | 
| **PASS-Val-03** | Validate leaving the new password field empty | Medium | Change password screen loaded | 1. Enter the old password <br> 2. Leave the New password field empty <br> 3. Fill the confirm password field with a valid password <br> 3. Click on the " Change password " field | System rejects the request, and a Validation error message appears near the new password field |
| **PASS-Val-04** | Validate leaving the confirm password field empty | Medium | Change password screen loaded | 1. Enter the old password <br> 2. Fill the New password field with a valid password. <br> 3. Leave the confirm password field empty <br> 3. Click on the " Change password " field | System rejects the request, and a Validation error message appears near the confirm password field |
| **PASS-Val-05** | Validate a mistake in the old password | Medium | Change password screen loaded | 1. Enter the old password with a mistake <br> 2. Fill in the new password and the confirmation password with the same valid password <br> 3. Click on the " Change password " field | System rejects the request, and a Validation error message appears near the old password field | 
| **PASS-VAl-06** | Validate the new and the confirm passwords mismatch | High | Change password screen loaded | 1. Enter the old password <br> 2. Fill in the new password with a valid password <br> 3. Fill the confirm password field with a different password <br> 4. Click on the " Change password " field | System rejects the request, and a Validation error message appears near the confirm password field |
| **PASS-VAl-07**| Validate the new and the confirm passwords match the old password | lw | Change password screen loaded | 1. Fill all fields with the same old password <br> 2. Click on the " Change password " field | System rejects the request, and a Validation error message appears indicating the new password matches the old password |

---

# Change Password - Security

| TC ID | Title | Priority | Preconditions | Steps | Expected Results | 
| --- | --- | --- | --- | --- | --- | 
| **PASS-Sec-01** | Valdiate using JavaScript inside the password fields | High | Change password fields loaded | 1. Enter a script inside any password field <br> 2. Click on the " Change password " button. | System won't execute the script, no sensitive data appears | 
| **PASS-Sec-02** | Validate the old password field is empty | High | Change password fields loaded | Observe the old password field content | System asks the user to fill the field & no data is appears |
| **PASS-Sec-03** | Validate the password is encrypted | High | Change password fields loaded | Observe the passwords | System shows the passwords encrypted | 


---

# Change Password - API 

| TC ID | Title | Priority | Preconditions | Steps | Expected Results | 
| --- | --- | --- | --- | --- | --- |
| **PASS-API-01** | Validate changing password status code | Medium | User is on Postman | Create a put request | Status code equals (200) |
| **PASS-API-02** | Validate changing password response time | Medium | User is on Postman | Create a put request | Response time must not exceed 300ms | 
| **PASS-API-03** | Validate the status code for a mistake in the address field | Medium | User is on Postman | Create a request | Status code equals (400) Bad request | 

> Response time based on best practices and UX performance standards

---

# My Account page - Usability Global

| TC ID | Title | Priority | Preconditions | Steps | Expected Results | 
| --- | --- | --- | --- | --- | --- |
| **Navigation-USAB-01** | Validate navigation via keybaord | Low | My Account page loaded | 1. Navigate to (Customer Info/Address/Change password) <br> 2. Click on the " Shift + Tab " buttons | 1. Focus moves to the next field when clicking on the " Tab " button <br> 2. Focus moves to the previous field when clicking on the " Shift + Tab " button  |
| **Cursor-USAB-02** | Validate cursor state change when hovering on different elements | Low | My account page loaded | Hover over different elements on the page | Curesor state changes depending on the (Element type & Action type) | 

---

# My Account page - UI 

| TC ID | Title | Priority | Preconditions | Steps | Expected Results | 
| --- | --- | --- | --- | --- | --- |
| **MandatoryFields-UI-01** | Validate all mandatory fields are marked | High | User is on Customer Info/Address/Password | Observe the mandatory fields design | The system shows a mark beside every mandatory field |
| **Align-UI-02** | Validate All elements aligned and no overlapping | High | My account page loaded | 1. Navigate to each section in the page | No overlap between page elements | 
| **Error-UI-03** | Validate error message content and place | Medium | My account page loaded | 1. Navigate to any section that requires input <br> 2. Leave a mandatory field empty <br> 3. Observe the error message | Error message appears near the empty mandatory field & the error message contains the right error information | 
| **Focus-UI-04** | Validate the selected section font style | My account page loaded | 1. Click on any section | The selected section text color changed |  

---

# My Account page - Compatibility

| TC ID | Title | Priority | Preconditions | Steps | Expected Results | 
| --- | --- | --- | --- | --- | --- |
| **Screen-Comp-01** | Validate page responsiveness with different screens | High | My account page loaded | 1. Navigate to the Developer's Tools <br> 2. Change the screen dimensions | 1. System displays the page correctly <br> 2. No overlapping <br> 3. Elements size changes accordingly <br> 4. Page's elements are placed in the right order |
| **Devices-Comp-02** | Validate page functionality across different devices | High | User has a different devices, & My account page loaded | 1. Make actions on the page | Page works in the same way throughout all devices |

---

# My Account page - Performance

| TC ID | Title | Priority | Preconditions | Steps | Expected Results | 
| --- | --- | --- | --- | --- | --- | 
| **PFM-01** | Validate My account sections' screen loading time | High | My Account page Loaded | 1. Navigate to any section <br> 2. Observe fields loading time | Loading time must not exceed 3s |
| **PFM-02** | Validate the page response with a 3G throttling internet | High | User has a 3G internet connection | 1. Navigate to My account page <br> 2. Observe the page's performance | Page operates correctly and response time < 3s |
| **PFM-03** | Validate page's sections buttons response time | Medium | My Account page Loaded | 1. Navigate to any section <br> 2. Fill the section's fields <br> 3. Click on the existing button | Loading time must not exceed 3s |
| **PFM-04** | Validate page response time with different internet connections | Medium | User has access to different internet connections & My account page loaded | 1. Navigate to any section <br> 2. Observe fields loading time | Loading time must not exceed 3s, and the page works correctly |

---

# Testing Scope Note

- Testing performed on live training environment.
- API-level testing and database validation are out of scope.
- Security penetration testing not included in this phase.
