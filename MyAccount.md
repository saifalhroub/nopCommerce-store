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

# AC - Order (cancel order)

Given the user hascancelled an order
When the user navigates to the order screen
Then no orders appear

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

