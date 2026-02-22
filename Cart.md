# Feature: <shopping Cart Page>

---

# 1️⃣ User Story
As a user,  
I want to have a cart page,  
So that I can check/finalize/edit the cart

## AC (Navigation):
 Given the user is using the store
 When the user clicks on the add to cart link
 Then the user will be redirected tothe shopping cart 

## AC (Products selected)
 Given the user is on the shopping cart page
 Then all the products added should appear

## AC (Quantity)
 Given that the user changed the quantity
 Then the total price changes accordingly

## AC (Remove)
 Given that the user is on the shopping cart page
 When the user clicks on the X icon under the name of the removed
 Then all of the product copies will be removed

## AC (Continue Shopping)
Given that the user clicked on the continue shopping button
Then the user will be redirected to the products page

## AC (Estimate shipping)
Given the user is on the shipping cart page
When the user clicks on the Estimate Shipping button
Then the user will be asked to provide:
 - Region (Country)
 - Zip/Postal code
And the estimated shipping price will show up

## AC (Gift Rapping)
Given the useris on the shopping cart
When the user decides to gift the products
Then the user can order the product to be gift-wrapped
And +10$ will be added to the total price

As a user,
I want a bill to see the total price and apply promo codes,
so I can have a discount and see the total price

## AC (price details)
Given the user is using the store
When the user is on the shopping cart page
Then he will see the total price that includes:
 - Sub-Total
 - Shipping price
 - Tax price
 - Total price

## AC (Discount Code)
Given the user is using the store 
When the user fills in the discount code field with a valid code
Then the discount will be applied to the bill
And the total price will change accordingly

## AC (Checkout)
Given the user is on the shopping cart
When the user is finished finalizing his order 
Then the user has to accept the terms of services
And then the user can use the checkout to proceed


---


#  Test Cases

---

## 2️⃣ Functional Test Cases (Happy Path)

| TC ID | Title | Priority | Pre-conditions | Steps | Expected Result |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TC-FUNC-01** | Validate cart link navigation | **High** | Store loaded | 1. Click "the cart link" | user is redirected to the shopping cart. |
| **TC-FUNC-02** | Validate removing a product from the cart | **High** | cart page loaded | 1. click on the X icon under the remove column | The products disappears |
| **TC-FUNC-03** | Validate updating product quantity using the increment/decrement arrows. | **High** |cart page loaded | 1. Click on the up/down arrows | the quantity changes accordingly.|
| **TC-FUNC-04** | Validate updating product quantity by typing a valid number. | **High** | Cart page loaded | 1. Click inside the quantity field <br> 2. Type in the quantity number | the quantity changes accordingly. |
| **TC-FUNC-05** | Validate updating quantity using keyboard arrow keys. | **Medium** | Cart page loaded | 1. Click inside the quantity field <br> 2. Click on the up and down keyboard keys | the quantity changes accordingly. | 
| **TC-FUNC-06** | Validate editing gift card details successfully. | **High** | Cart page loaded | 1. Click on the edit link <br> 2. Update the card gift information <br> 3. Click on the update button | the modification must be saved, and no duplicate products will appear |
| **TC-FUNC-07** | Validate estimating shipping cost with valid data. | **High** | Cart page loaded | 1. Click on the Estimate shipping button <br> 2. Fill all required fields <br> 3. Click on the apply button. | A list of shipping methods must appear. The user will be able to select a method. Each method has its price. selecting a method would change the total price accordingly | 
| **TC-FUNC-08** | Validate "Continue Shopping" button navigation. | **High** | Cart page loaded | 1. Click on the continue shopping button | The user will be redirected to the products page. |
| **TC-FUNC-09** | Validate "Checkout" button navigation. | **High** | Cart page loaded | 1. Determine the shipping destination and method <br> 2. Accept the terms of service <br> 3. Click on the "Checkout" button | The user will be redirected to the Checkout page. |
| **TC-FUNC-10** | Verify subtotal updates dynamically when quantity changes. | **High** | Cart page loaded | 1. Change the product quantity <br> 2. Observe the subtotal calculation | the subtotal price changes dynamically. |
| **TC-FUNC-11** | Verify the total price recalculates correctly after quantity update. | **High** | Cart page loaded | 1. Change the product quantity <br> 2. Observe the total calculation | the total price changes dynamically. |
| **TC-FUNC-12** | Validate products persist after refreshing the cart page. | **Medium** | Cart page loaded, and the cart contains products| 1. Refresh the shopping cart page <br> 2. Observe the products persist | All products will still exist. The subtotal and total price won't change. |
| **TC-FUNC-13** | Validate products persist after logout → login. | **Medium** | Cart page loaded, and the cart contains products| 1. Logout <br> 2. Login <br> 3. Navigate to the shopping cart <br> 4. Observe the products persist | All products will still exist. The subtotal and total price won't change. |
| **TC-FUNC-14** | Validate products persist after closing and reopening the browser. | **Medium** | Cart page loaded, and the cart contains products| 1. Close the browser <br> 2. Open the browser <br> 3. Navigate to the store <br> 4. Navigate to the shopping cart <br> 5. Observe the products persist | All products will still exist. The subtotal and total price won't change. |
| **TC-FUNC-15** | Verify quantity increments correctly (one unit at a time). | **High** | Cart page loaded | 1. Change the product quantity using the increment/decrement icons <br> 2. Observe the change in quantity each  time  | Only one unit is added for each click. |
---
## Functional – Invalid Scenarios

| TC ID | Title | Priority | Pre-conditions | Steps | Expected Result |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TC-FUNCINV-01** | | | |

**Steps:**
1.  
2.  

**Expected Result:**
-  
-  

---

## Boundary Value Testing

| Field | Min | Max | Tested Value | Expected |
|-------|-----|-----|-------------|----------|

---

## Edge Cases

| TC ID | Scenario | Expected Result |
|-------|----------|----------------|

---

## Security Testing

| TC ID | Attack Type | Expected Result |
|-------|------------|----------------|

---

## UI Testing

- Layout validation  
- Field alignment  
- Button state  
- Error message placement  

---

## Usability Testing

- Keyboard navigation  
- Field focus behavior  
- Error clarity  
- Mandatory indicators  

---

## Compatibility Testing

- Keyboard navigation  
- Field focus behavior  
- Error clarity  
- Mandatory indicators  

---

## API Testing (If applicable)

### Valid Request
- Status Code:
- Response Body:
- Database Check:

### Invalid Request
- Status Code:
- Error Message:
- Data Integrity:
