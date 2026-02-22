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

## 2️⃣Functional Test Cases (Happy Path)

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
| **TC-FUNCINV-01** | Validate checkout without accepting Terms of Service. | High | Cart page loaded | 1. Do not accept Terms of Service <br> 2. Observe the system response. | 1. The user will be prohibited from proceeding to the checkout page <br> 2. An error message will appear notifying the user that he has to accept the terms of service |
| **TC-FUNCINV-02** | Validate checkout with no internet connection. | low | Cart page loaded | 1. Cut-off the internet connection <br> 2. Click on the Checkout button. | 1. The user will be prohibited from proceeding to the checkout page <br> 2. The user will be redirected to a no internet connection page |
| **TC-FUNCINV-03** | Validate applying an invalid discount code. | High | Cart page loaded | 1. Fill the discount field with an invalid code <br> 2. Click on the Apply button | 1. The code will be rejected <br> 2. An error message will appear saying: "The code is invalid". |
| **TC-FUNCINV-04** | Validate applying an invalid gift card code. | High | Cart page loaded | 1. Fill the gift card field with an invalid code <br> 2. Click on the Apply button | 1. The code will be rejected <br> 2. An error message will appear saying: "The code is invalid". |

---



## Edge & Security

| TC ID | Title | Priority | Pre-conditions | Steps | Expected Result |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TC-Edge-01** | Validate entering zero in the quantity field. | low | Cart page loaded. User has products in the cart | 1. Fill the quantity field with zero <br> 2. Observe the system response | 1. The product will be removed from the cart <br> 2. The subtotal and total will change accordingly |
| **TC-Edge-02** | Validate leading/trailing spaces in the quantity field. | low | Cart page loaded. User has products in the cart |  1. Fill the quantity field with a leading/trailing space <br> 2. Click outside the quantity field | 1. The system will remove the space and neglect it |
| **TC-Edge-03** | Validate entering an extremely large number in quantity. | High | Cart page loaded. User has products in the cart | 1. Fill the quantity field with an extremely large number <br> 2. Click outside the quantity field | Request denied, the quantity number placed inside the quantity field is the old one |
| **TC-Edge-04** | Validate decimal numbers in the quantity field. | High | Cart page loaded. User has products in the cart | 1. Fill the quantity field with a decimal number <br> 2. Click outside the quantity field | Request denied, the quantity number placed inside the quantity field is the old one |
| **TC-Edge-05** | Speacial characteres inside the quantity field | low | Cart page loaded. User has products in the cart | 1. Fill the quantity field with a decimal number <br> 2. Click outside the quantity field | Request denied, the quantity number placed inside the quantity field is the old one |
| **TC-Edge-06** | Copy & Paste into the quantity field | low | Cart page loaded. User has products in the cart. Note app to write and copy the number from | 1. Navigate to the note app <br> 2. Write the number <br> 3. Select and copy the number <br> 4. Navigate to the shopping cart <br> 5. Paste the number inside the quantity field. | System accepts the pasted number. No crash |
| **TC-Edge-07** | Validate extremely long string in discount field (1000+ characters). | low | Cart page loaded. User has products in the cart | 1. Enter a (+1000 character) inside the discount field | 1. Code is rejected <br> 2. No change to the total price |
| **TC-SEC-01** | Validate entering a negative number (e.g., -115). | High | Cart page loaded. User has products in the cart | 1. Enter -115 in the quantity field <br> 2. Click outside the quantity field | 1. The number is rejected <br> 2. The old number is the one still processed <br> 3. Proper validation message appears |
| **TC-SEC-02** | Validate entering JavaScript code in the discount field. | high | Cart page loaded. User has products in the cart | 1. Enter <script>alert('test')</script> in discount field <br> 2. Click Apply | 1. Script is not executed <br> 2. Input is sanitized <br> 3. Proper validation message appears |
| **TC-SEC-03** | Validate entering JavaScript code in the gift card code field. | high | Cart page loaded. User has products in the cart |  1. Enter <script>alert('test')</script> in gift card field <br> 2. Click Apply | 1. Script is not executed <br> 2. Input is sanitized |
| **TC-SEC-04** | Validate SQL injection attempt in quantity field (e.g., ' OR '1'='1) | High | Cart page loaded. User has products in the cart | 1. Enter (' OR '1'='1) in the quantity field <br> 2. Click outside the quantity field | 1. The injection is not executed <br> 2. The system restores the old number |

---

## UI Validation

| TC ID | Title | Priority | Pre-conditions | Steps | Expected Result |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TC-UI-01** | Validate mandatory fields are clearly marked | High | Cart page loaded | Observe the page mandatory fields | All mandatory fields have a star sign beside them | 
| **TC-UI-02** | Validate correct rror messages appear | High | Cart page loaded | 1. Do not accept the terms of service <br> 2. Click on the Checkout button | 1. System rejects the order <br> 2. "You have to accept the terms of service" error message appears | 
| **TC-UI-03** | Validate cart elements alignment. | High | Cart page loaded | Observe the page elements alignment | 1. No overlapping between page's elements | 
| **TC-UI-04** | Validate consistent font styles. | Medium | Cart page loaded | Observe the font style across the page | All headers have the same style, all paragraphs have the same style | 


---

## Usability Testing

| TC ID | Title | Priority | Pre-conditions | Steps | Expected Result |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TC-USB-01** | Validate keyboard navigation (Tab, Shift+Tab). | low | Cart page loaded | 1.  Click on the tab button to move to the next element <br> 2. Click on the "tab+shift" buttons to move to the previous element | 1. Focus will move to the next element each time the user presses "tab" button <br> 2. Focus will move to the previous element each time the user presses the "tab+shift" buttonس |
| **TC-USB-02** | Validate page compatibility with screen readers. | High | Cart page loaded, Screen reader is active |  |  |

---

## Compatibility Testing

| TC ID | Title | Priority | Pre-conditions | Steps | Expected Result |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TC-COM-01** | Validate responsiveness across devices (Desktop / Tablet / Mobile). | High | User is using the store via (Desktop/Tablet/Mobile) | Observe the page responsivity for all devices | The store is responsive to all of the devices | 
| **TC-COM-02** | Validate functionality across different operating systems for PC | High | User has access to the store via Windows & linux | Test the store functionality with the two operating systems | The store works correctly without any errors | 
| **TC-COM-03** | Validate compatibility across major browsers for PC | High | User is using the store via Chrome & Edge | Make sure the store is compatible for both browsers | The store works correctly without any errors | 
| **TC-COM-04** | Validate behavior under slow network conditions (e.g., 3G throttling). | High | User is using the app wit 3G internet | Observe the page behavior | No crash, the store works normally |  

---

## API Testing (If applicable)

| TC ID | Title | Priority | Pre-conditions | Steps | Expected Result |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TC-API-01** | Validate error response when invalid quantity is sent. | High | User logged in, item in cart. | Send PATCH `/cart` with quantity = -1. | HTTP 400 with error message: "Quantity must be positive". |
| **TC-API-02** | Validate checkout API fails if Terms are not accepted. | High | User logged in, cart has items. | Send POST `/checkout` with `termsAccepted = false`. | HTTP 422 with error: "You must accept the terms". |
| **TC-API-03** | Validate backend validation even if frontend validation is bypassed. | Medium | Valid session, product in cart. | Using Postman, send request with quantity = 0 or missing fields. | Backend returns 400/422 and rejects request. |
| **TC-API-04** | Validate correct request payload structure. | Medium | API documentation available. | Send full valid payload to create a resource. | HTTP 201 with correct response body. |

---

## Performance Testing

| TC ID | Title | Priority | Pre-conditions | Steps | Expected Result |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TC-PFM-01** | Validate response time for Continue Shopping button | High | Cart page loaded | 1. Click on the Continue shopping button <br> 2. Observe the redirection response time | response time is ≤ 3 seconds  |  
| **TC-PFM-02** | Validate response time for Checkout button | High | Cart page loaded | 1. Accept terms of service <br> 2. Click on checkout <br> 3. Observe the redirection response time | response time is ≤ 3 seconds |  
| **TC-PFM-03** | Validate response time for Applying discount code | High | Cart page loaded | 1. Enter the discount code <br> 2. Click on apply <br> 3. Observe the code application process response time | response time is ≤ 3 seconds |  
| **TC-PFM-04** | Validate response time for Applying gift card code | High | Cart page loaded | 1. Enter the gift card code <br> 2. Click on apply <br> 3. Observe the code application process response time | response time is ≤ 3 seconds |  
| **TC-PFM-05** | Validate response time for Estimating shipping | High | Cart page loaded | 1. Click on the estimate shipping button <br> 2. Fill all mandatory fields <br> 3. Click on the apply button <br> 4. Observe the estimation response time | response time is ≤ 3 seconds |  
| **TC-PFM-06** | Validate response time for Subtotal & total recalculation | High | Cart page loaded | 1. Change the product quantity <br> 2. Observe the subtotal & total recalculation response time | response time is ≤ 3 seconds |

- Based on industry-standard performance benchmarks (Google/Amazon studies) and the nature of the application, the expected response time thresholds are set as follows:

  - Page load / critical transactions: ≤ 3 seconds (the threshold beyond which 40% of users abandon the site).

  - API/backend calls: ≤ 500 ms (to ensure a smooth user experience).
