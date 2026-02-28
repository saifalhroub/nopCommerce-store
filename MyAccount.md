# Feature: MY Account page

---

# User story:

> As a user,
> I want to have a "My Account" Page,
> So I can manage my account & have a clear view of my actions

---

# AC - My account page structure

Given the user is logged in 
When the user clicks on the My Account button
Then the user will be redirected to My Account page
And the page shows the following elements in a side list:
  - Customer info
  - Address
  - Orders
  - Recurring payments
  - Downloadable products
  - Back in stock subscription
  - Reward points
  - Change password
  - My products review

---

# AC - Active element state

Given the user is on the My account page
When the user selects an element from the list
Then:
  - The screen content changes
  - The selected elements' text color change
  - The Title on screen matches the selected element

---

# AC - Customer Info structure

 Given the user selects customer info
 When the page load successfully
 The user will see:
  - Your Personal Details (Mandatory)
   - Gender
   - First name
   - last name
   - Email
  - Company Details (Optional)
   - Company name 
  - Subscribe to newsletter (Optional)
   - Newsletter 
---

# AC - Customer Info core

Given that the user filled all the required fields with valid data
When the user clicks on save
Then:
  - The system will replace the old data with the new data
  - The system sends a confirmation message: The customer info has been updated successfully.
And the system will allow the user to log in using the new details

--- 

# AC - Customer Info (same old data)

Given that the user used the same old details
When the user clicks on the save button
Then:
  - Validation error message telling the user: New details match the old ones
  - No crash

---

AC - Customer Info (Negative)

Given that the user leaves a mandatory field empty
When the user clicks on the save button
Then:
  - A validation error message will appear near the field
  - The system sends the user to the field, and the field is active

---

# AC - Address (No previous address)

Given that the user is on the Address section
When the user has no previously saved address
Then:
  - No address to be selected
  - Add new address button Appears

---

# Ac - Address (structure)

Given the user clicks on the add new address button
When the page loads
The the displayed fields are:
  - First Name (Mandatory)
  - Last Name (Mandatory)
  - Email (Mandatory)
  - Company
  - Country (Mandatory)
  - State/province 
  - City (Mandatory)
  - Address 1 (Mandatory)
  - Address 2
  - Zip/postal code (Mandatory)
  - Phone number (Mandatory)
  - Fax number
  - Save button

---

# AC - Address core

Given that the user filled all the required fields with valid data
When the user clicks on save
Then:
  - The system will replace the old data with the new data
  - The system sends a confirmation message: The new address has been added successfully.
And the address will appear in any purchase operation

---

# AC - Address (same old data)

Given that the user used the same old details
When the user clicks on the save button
Then:
  - Validation error message telling the user: New details match the old ones
  - No crash

---

# AC - Address (Negative)

Given that the user leaves a mandatory field empty
When the user clicks on the save button
Then:
  - A validation error message will appear near the field
  - The system sends the user to the field, and the field is active

---

# AC - Address (already saved address)

Given the user has a saved address
When it is on the address screen
Then the screen will show:
  - The old address details
  - Delete Address
  - Edit Address
  - Add New Address

---

# AC - Address (More than one address)

Given the user already has a saved address
When the user adds a new address
Then both the old and the new addresses will be shown

---

# AC - Orders core

Given the user wants to take a look at his orders
When the user clicks on the Orders section
Then the user will see:
  - Order number
  - Order status
  - Order date

---

# AC - Orders (cancel order)

Given the user has cancelled an order
When the user navigates to the order screenص
Then no orders appear

---

# AC - Orders (Filter)

Given the user is on the Orders page
When the user selcets order date filter
Then the orders that do not match the criteria will disappear

---

# AC - Recurring payment

Given the user has a recurring payment 
When the user is on the My account page
Then the user can see all of their recurring payments

---

# AC - Back in stock subscriptions

Given the user is on my account page
When the user clicks on the Back in stock subscriptions
Then the system will preview the subscriptions the user made  

---

# AC - Reward points

Given the user is on the reward points section
When the user made purchases more than 10$ 
Then the system will sum up all points 
And the user will be able to see the total points

**Business logic**:
  - every 10$ = 1 reawrd point
  - if the user bought a product with a price of 139$, then he will get 13 reward points

---

# AC - Downloadable products

Given the user is on My account page
When the user clicks on the Downloadable products link
Then all products appear
And a download link will appear for the downloadable products

---

# AC - Change Password structure

Given the user clicks on the change password link 
When the page loads
Then the user will see:
  - Old Password
  - Forgot Password
  - New Password
  - Confirm Password
  - Change password button

# Business roles:
  - All fields are marked as required
  - If the user forgot his password, then the system will allow him to reset his password via email

---

# AC - Change Password Core functionality

Given the user is on the change password page
When the user change his password
Then:
   - A confirmation message will appear
   - The user can use the new password to log in

---

# AC - Change password (New pass = Old Pass)
Given that the user uses the same old password in the new password field
When the user clicks on the " Change Password " button
Then:
  - A Validation error message indicating that the new password should not match the old password
  - And the focus should be on the new password field

---

# AC - Change password Validation

Given that the user left a field empty
When the user clicks on the " Change Password " button
Then A validation error message indicating that ( ____ filed is required)

-----------------------------------------------------------------------------------------------------------------------------------------------------
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!

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

# Testing Scope Note

- Testing performed on live training environment.
- API-level testing and database validation are out of scope.
- Security penetration testing not included in this phase.
