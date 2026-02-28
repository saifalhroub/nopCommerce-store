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

# Customer Info - Core functional

| TC ID | Title | Priority | Preconditions | Steps | Expected Results | 
| --- | --- | --- | --- | --- | --- |
| **CustomerInfo-Fun-01** | Validate updating any field in the customer info's | High | Customer info fields loaded | 1. Edit the data of the required field <br> 2. Click on the save button | 1. Data is updated successfully <br> 2. Success change info message: (The customer info has been updated successfully.) <br> 3. The system placed the new data inside the fields <br> user is allowed to  log in using the new data |

--- 

# Customer Info - Validation

| TC ID | Title | Priority | Preconditions | Steps | Expected Results | 
| --- | --- | --- | --- | --- | --- |
| **CustomerInfo-Val-01** | Validate leaving a required field empty | Medium | Customer info fields loaded | 1. Erase any required field data <br> 2. Click on the " Save " button | 1. Request is rejected <br> 2. A validation error message appears near the empty required field | 
| **CustomerInfo-Val-02** | Validate using a wrong format new email | High | Customer info fields loaded | 1. Fill the email field with a wrong format email (saas@asas) <br> 2. Click on the " Save " button | 1. Request is rejected <br> 2. A validation error message appears indicating that (Wrong Email) is used | 

# Testing Scope Note

- Testing performed on live training environment.
- API-level testing and database validation are out of scope.
- Security penetration testing not included in this phase.
