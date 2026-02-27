# 🚀 Feature: Shopping Cart Page

---

# 1️⃣ User Story

As a user,  
I want to view and manage the items in my cart,  
So that I can review, edit, and finalize my purchase.

---

## Acceptance Criteria

### AC (Navigation)
Given the user is browsing the store  
When the user clicks on the cart link  
Then the user is redirected to the Shopping Cart page  

---

### AC (Products Display)
Given the user has added products to the cart  
When the user navigates to the Shopping Cart page  
Then all added products should be displayed correctly  

---

### AC (Quantity Update)
Given the user changes the product quantity  
When the quantity is updated  
Then the subtotal and total prices should update dynamically and accurately  

---

### AC (Remove Product)
Given the user is on the Shopping Cart page  
When the user clicks on the remove (X) icon  
Then all quantities of that product are removed from the cart  
And the subtotal and total are updated accordingly  

---

### AC (Continue Shopping)
Given the user is on the Shopping Cart page  
When the user clicks the "Continue Shopping" button  
Then the user is redirected to the products page  

---

### AC (Estimate Shipping)
Given the user is on the Shopping Cart page  
When the user clicks on "Estimate Shipping"  
Then the user is asked to provide:
- Country / Region  
- Zip / Postal Code  
And the estimated shipping methods and prices are displayed  

---

### AC (Gift Wrapping)
Given the user is on the Shopping Cart page  
When the user selects the gift wrapping option  
Then an additional $10 is added to the total price  
And the total price updates accordingly  

---

### AC (Price Details)
Given the user is on the Shopping Cart page  
Then the user should see a detailed price breakdown including:
- Subtotal  
- Shipping  
- Tax  
- Total  

---

### AC (Discount Code)
Given the user enters a valid discount code  
When the code is applied  
Then the discount is reflected in the total price  
And the total price updates accordingly  

---

### AC (Checkout-Registered)
Given that the user is on the cart page as a registered customer
When the user is making a valid checkout
Then the user is redirected to the Checkout page  

---

## AC (Checkout-Guest)
Given that the user is on the cart page as a guest 
When the user is making a valid checkout
Then the user is redirected to the register/login page
And the user can select (Checkout as a guest) 
---

# 2️⃣ Functional Test Cases (Happy Path)

| TC ID | Title | Priority | Pre-conditions | Steps | Expected Result |
| :--- | :--- | :--- | :--- | :--- | :--- |
| TC-FUNC-01 | Validate cart link navigation | High | Store loaded | Click cart link | User is redirected to Shopping Cart page |
| TC-FUNC-02 | Validate removing a product | High | Cart page loaded | Click remove (X) icon | Product is removed; subtotal & total updated |
| TC-FUNC-03 | Validate quantity update using arrows | High | Cart page loaded | Click increment/decrement arrows | Quantity updates by 1 per click; totals recalculate |
| TC-FUNC-04 | Validate quantity update by typing | High | Cart page loaded | Enter valid number in quantity field | Quantity updates; totals recalculate |
| TC-FUNC-05 | Validate quantity update using keyboard arrows | Medium | Cart page loaded | Use keyboard up/down keys | Quantity updates correctly; totals recalculate |
| TC-FUNC-06 | Validate editing gift card details | High | Cart page loaded | Edit gift card → Update | Changes saved; no duplicate item created |
| TC-FUNC-07 | Validate estimating shipping | High | Cart page loaded | Estimate shipping with valid data | Shipping methods displayed; total updates when selected |
| TC-FUNC-08 | Validate Continue Shopping button | High | Cart page loaded | Click Continue Shopping | User redirected to products page |
| TC-FUNC-09 | Validate Checkout navigation | High | Cart page loaded | Accept Terms → Click Checkout | Redirected to Checkout page |
| TC-FUNC-10 | Verify subtotal updates dynamically | High | Cart page loaded | Change quantity | Subtotal updates instantly without page reload |
| TC-FUNC-11 | Verify total recalculation accuracy | High | Cart page loaded | Change quantity | Total = Subtotal + Tax + Shipping (correct formula) |
| TC-FUNC-12 | Validate cart persistence after refresh | Medium | Cart contains products | Refresh page | Products remain; totals unchanged |
| TC-FUNC-13 | Validate cart persistence after logout/login | Medium | Cart contains products | Logout → Login → Open cart | Products persist correctly |
| TC-FUNC-14 | Validate cart persistence after closing browser | Medium | Cart contains products | Close browser → Reopen → Open cart | Products persist correctly |
| TC-FUNC-15 | Verify quantity increments one by one | High | Cart page loaded | Click increment multiple times | Quantity increases by exactly 1 per click |
| TC-FUN-16 | Checkout as a guest | High | Cart page loaded | Accept Terms → Click Checkout | 1. User is redirected to the register/login page <br> 2. User can select checkout as a guest |

---

# Functional – Invalid Scenarios

| TC ID | Title | Priority | Pre-conditions | Steps | Expected Result |
| :--- | :--- | :--- | :--- | :--- | :--- |
| TC-FUNCINV-01 | Checkout without accepting Terms | High | Cart page loaded | Do not accept Terms → Click Checkout | Checkout blocked; clear validation message displayed |
| TC-FUNCINV-02 | Checkout with no internet | Medium | Cart page loaded | Disable internet → Click Checkout | Request fails gracefully; user sees network error message |
| TC-FUNCINV-03 | Invalid discount code | High | Cart page loaded | Enter invalid code → Apply | Code rejected; clear error message; total unchanged |
| TC-FUNCINV-04 | Invalid gift card code | High | Cart page loaded | Enter invalid code → Apply | Code rejected; clear error message; total unchanged |


---

# Edge & Security Testing

| TC ID | Title | Priority | Pre-conditions | Steps | Expected Result |
| :--- | :--- | :--- | :--- | :--- | :--- |
| TC-EDGE-01 | Quantity = 0 | Medium | Cart contains products | Enter 0 | Product removed OR validation shown (based on requirements); totals update |
| TC-EDGE-02 | Leading/trailing spaces | Low | Cart contains products | Enter " 5 " | Spaces trimmed; value processed correctly |
| TC-EDGE-03 | Extremely large quantity | High | Cart contains products | Enter large number (e.g., 9999999) | Request rejected; validation message shown |
| TC-EDGE-04 | Decimal quantity | High | Cart contains products | Enter 2.5 | Validation error; quantity remains unchanged |
| TC-EDGE-05 | Special characters | Medium | Cart contains products | Enter !@#$% | Validation error; no crash |
| TC-EDGE-06 | Copy & Paste quantity | Low | Cart contains products | Paste valid number | Value accepted; no crash |
| TC-EDGE-07 | Long string in discount field | Medium | Cart contains products | Enter 1000+ characters | Input rejected; no performance degradation |

| TC-SEC-01 | Negative quantity | High | Cart contains products | Enter -115 | Validation error; old quantity restored |
| TC-SEC-02 | XSS in discount field | High | Cart contains products | Enter `<script>alert('test')</script>` | Script not executed; input sanitized |
| TC-SEC-03 | XSS in gift card field | High | Cart contains products | Enter `<script>alert('test')</script>` | Script not executed; input sanitized |
| TC-SEC-04 | SQL Injection attempt | High | Cart contains products | Enter `' OR '1'='1` | Injection blocked; input sanitized |

---

# UI Validation

| TC ID | Title | Priority | Pre-conditions | Steps | Expected Result |
| :--- | :--- | :--- | :--- | :--- | :--- |
| TC-UI-01 | Mandatory fields marked clearly | High | Cart page loaded | Observe fields | Required fields marked with * and proper styling |
| TC-UI-02 | Proper error message display | High | Cart page loaded | Trigger validation error | Error displayed near field; readable; styled consistently |
| TC-UI-03 | Layout alignment | High | Cart page loaded | Inspect layout | No overlapping; proper spacing; responsive alignment |
| TC-UI-04 | Consistent font styles | Medium | Cart page loaded | Inspect typography | Headers & text follow consistent design system |

---

# Usability Testing

| TC ID | Title | Priority | Pre-conditions | Steps | Expected Result |
| :--- | :--- | :--- | :--- | :--- | :--- |
| TC-USB-01 | Keyboard navigation | Medium | Cart page loaded | Use Tab / Shift+Tab | Focus moves logically; no focus trap |
| TC-USB-02 | Screen reader compatibility | High | Screen reader active | Navigate through cart | All elements announced correctly; buttons labeled; images have alt text; totals announced properly |

---

# Compatibility Testing

| TC ID | Title | Priority | Pre-conditions | Steps | Expected Result |
| :--- | :--- | :--- | :--- | :--- | :--- |
| TC-COM-01 | Responsive design | High | Desktop/Tablet/Mobile | Resize viewport | No horizontal scroll; layout adapts correctly |
| TC-COM-02 | OS compatibility | High | Windows / Linux | Test functionality | No layout issues; no console errors |
| TC-COM-03 | Browser compatibility | High | Chrome / Edge | Test full flow | No functional or UI differences |
| TC-COM-04 | Slow network (3G) | High | Throttled network | Test interactions | No crashes; graceful loading indicators |

---

# API Testing

| TC ID | Title | Priority | Steps | Expected Result |
| :--- | :--- | :--- | :--- | :--- |
| TC-API-01 | Invalid quantity | High | Send quantity = -1 | HTTP 400; validation error |
| TC-API-02 | Checkout without terms | High | POST checkout with termsAccepted=false | HTTP 422; validation error |
| TC-API-03 | Backend validation bypass | Medium | Send invalid payload via Postman | Request rejected |
| TC-API-04 | Correct payload structure | Medium | Send valid request | HTTP 200/201; correct response body |

---

# Performance Testing

| TC ID | Title | Priority | Expected Threshold |
| :--- | :--- | :--- | :--- |
| TC-PFM-01 | Continue Shopping response time | High | ≤ 3 seconds |
| TC-PFM-02 | Checkout response time | High | ≤ 3 seconds |
| TC-PFM-03 | Apply discount response time | High | ≤ 3 seconds |
| TC-PFM-04 | Apply gift card response time | High | ≤ 3 seconds |
| TC-PFM-05 | Estimate shipping response time | High | ≤ 3 seconds |
| TC-PFM-06 | Subtotal & total recalculation | High | ≤ 500 ms |

---

Performance thresholds are based on industry standards:

- Page load / critical transactions: ≤ 3 seconds  
- Backend/API calls: ≤ 500 ms  




-------------------------------------------------------------------------------------------------------------
# Shopping Cart 
---

# 1️⃣ User Story
ِAs a user,
I want to view and manage the items in my cart,
So that I can review and finalize my purchase

## AC (Navigation):
 Given the user is using the store
 When the user clicks on the add to cart link
 Then the user will be redirected tothe shopping cart 

## AC (Products selected)
Given the user has added products to the cart
When the user navigates to the cart page
Then all selected products should be displayed

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
