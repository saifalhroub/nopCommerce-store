# Checkout

## 1-
> As a user, 
> I want a checkout page,
> So I can use my personal information to confirm my purchase

---

### AC (Billing Address)

 Given that the user wants to confirm identity
 When the user is on the checkout page
 Then he has to provide his billing address informationsto confirm identity


## AC (Billing Address - Save info)
Given the user is on the billing address form
When the user clicks onsave
Then the user will be saved in the database
And the user can use it for other orders

## AC (Billing Address - shipping to the same address0
Given the user selected ship to the same address
When the user clicks on the continue button
Then the shipping address section will be skipped
And the shipping address will be the same as of the billing address
---

### AC - (Shipping Address)

Given the user is on the checkout page
When the user completed the billing address step
Then he will be asked to provide a shipping destination

---

### AC (Shipping Method)

Given the user is on the checkout page
When the user completed the shipping address step
Then the user will be redirected to shipping method page
And three shipping methods will be available:
  - Land Transport
  - Air Shipping one day
  - Air Shipping two days

---

### AC - (Payment Method)

Given the user is on the checkout page
When the user completed the shipping method step
Then two payment methods will appear:
 - Check / Money Order
 - Credit Card
And the user has to select a method

---

### AC - (Payment information)

 - **Check / Money Order**
   
Given the user selects "Check / Money Order" as a payment method  
When the user proceeds to the Payment Information step  
Then the system should display:
  - Company name
  - Full mailing address
  - Payment instructions text
  - Notice about check clearance delay
  - No Input Required

- Given the user selects Check / Money Order  
Then the system should not require additional payment input fields  
And the user can proceed directly by clicking Continue

- **Credit Card**

  Given the user selects Credit Card
  When the user proceeds to the payment information step
  Then the user will be asked to provide this
    - Select credit card
    - Cardholder name
    - Card number
    - Expiration date
    - Card code
 


---
### AC (Confirm order)

Given the user completed the payment information step
When the user is on the confirm order step
Then the system should display:
  - Billing Address
  - Shipping Address
  - Shipping Method
  - Payment Method
  - Payment Information
  - The subtotal, shipping, tax & total prices
  - The items added to the cart
  - Back button
  - Confirm button

---

### AC - Confirm button
Given that the user is on the confirm order step
When the user clicks on confirm button
Then the order will be placed
And the user will be redirected to the Thanking page

---

### AC – Navigation – (Back Button)

Given the user is on any of the checkout page steps  
When the user clicks on the Back button  
Then the user should be redirected to the previous checkout step

---

### AC – (Continue Button)

Given the user is on any of these checkout page steps
  - Billing Address
  - Shipping Address
  - Shipping Method
  - Payment Method
  - Payment Information
When the user clicks on the Continue button  
Then the system should proceed to the next checkout step


> As a user,
> I want an order confirmation screen
> So I know the order has been accepted

### AC - Confirmation message
Given the user finished the checkout process
Then the user will be redirected to thank-you page
And the user will see:
  - Thank you 
  - Your order has been successfully processed!
  - Order number

---

### AC - Order details
Given the user is on the thank-you page
When the user clicks on order details
Then the user will be redirected to the order information page

---

### AC - Continue button
Given the user is on the thank-you page
When the user clicks on the continue button
Then the user will be redirected to the landing page

---
# Functional Positive “Billing Address”

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| --- | --- | --- | --- | --- | --- |
| **TC-FUNV-01** | Using valid bill information without checking the ship to the same address radio box | High | Checkout page loaded | 1. Fill all mandatory fields <br> 2. Uncheck the ship to the same address radio box <br> 3. Click on continue | 1. No validation error <br> 2. user is redirected to the Shipping Address section |
| **TC-FUNV-02** | Validate leaving optional fields empty | low | Checkout page loaded | 1. Fill all mandatory fields <br> 2. Leave all unmarked/optional fields empty <br> 3. Click on continue | 1. No validation error <br> 2. user is redirected to the Shipping Address section |
| **TC-FUNV-03** | Validate checking the ship to the same address radio box | high | Checkout page loaded | 1. Fill all mandatory fields <br> 2. Check the "ship to the same address" radio box  <br> 3. Click on continue | 1. No validation error <br> 2. user is redirected to the Shipping method section |
| **TC-FUNV-04** | Validate Selecting a saved address | High | 1. User set up his address on my account  | 1. Navigate to the checkout page <br> 2. Observe the bill address  available address | User can select the address he saved from my account page | 
| **TC-FUNV-05** | Validate First name, last name & email autofilled | low | Bill Address fields loaded | 1. Observe the First name, last name & email fields | 1. All fields are autofilled <br> 2. User can modify them |
| **TC-FUNV-06** | Validate the state/province change based on the selected country  | high | Bill Address fields loaded | 1. Select a country <br> 2. Navigate to the state/province drop-down list <br> 3. Observe the options <br> 4. Repeat the procedure for more countries | 1. State/province changes each time the user changes the selected country |

---

# Functional Negative “Billing Address”
| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| --- | --- | --- | --- | --- | --- |
| **TC-FUNINV-01** | Leaving all mandatory fields empty | High | Billing fields loaded | 1. Leave all mandatory fields empty <br> 2. Click on continue | 1. Request denied <br> 2. User remains int billing address section <br> 3. Validation error message for all mandatory fields | 
| **TC-FUNINV-02** | Selecting state/province without selecting the country | low | Billing fields loaded | 1. Do not select the country <br> 2. select the state/province | User not allowed to select the state unless he selects the country |
| **TC-FUNINV-03** | Using wrong fromat email | high | Billing fields loaded | 1. make a mistake on the email format <br> 2. fill mandatory fields <br> 3. Click on the continue button | 1. Request is denied <br> 2. User won't be redirected to the shipping address section <br> 3. validation error message indicating the usage of invalid email |
| **TC-FUNINV-04** | Using only spaces in the mandatory fields | medium | Billing fields loaded | 1. Fill all mandatory fields with only spaces <br> 2. Click on the continue button | 1. Request is denied <br> 2. Validation error message indicating the mandatory field have invalid data |
| **TC-FUNINV-05** | Leave first name empty | high | Billing fields loaded | 1. Leave the first name field empty <br> 2. Fill all mandatory fields<br> 3. Click on continue | 1. Request is denied <br> 2. User won't be redirected to the shipping address section <br> 3. validation error message indicating the first name field is required |
| **TC-FUNINV-06** | Leave last name empty | hgh | Billing fields loaded | 1. Leave the last name field empty <br> 2. Fill all mandatory fields <br> 3. Click on continue | 1. Request is denied <br> 2. User won't be redirected to the shipping address section <br> 3. validation error message indicating the last name field is required |
| **TC-FUNINV-07** | Leave email empty  | high | Billing fields loaded | 1. Leave the email field empty <br> 2. Fill all mandatory fields <br> 3. Click on continue | 1. Request is denied <br> 2. User won't be redirected to the shipping address section <br> 3. validation error message indicating the email field is required |
| **TC-FUNINV-08** | Leave address 1 empty | High | Billing fields loaded | 1. Leave the address 1 field empty <br> 2. Fill all mandatory fields <br> 3. Click on continue |  1. Request is denied <br> 2. User won't be redirected to the shipping address section <br> 3. validation error message indicating the address 1 field is required |
| **TC-FUNINV-09** | Leave city empty | High | Billing fields loaded | 1. Leave the city field empty <br> 2. Fill all mandatory fields <br> 3. Click on continue | 1. Request is denied <br> 2. User won't be redirected to the shipping address section <br> 3. validation error message indicating the city field is required |
| **TC-FUNINV-10** | Leave postal code / Zip empty | High | Billing fields loaded | 1. Leave the postal code/zip field empty <br> 2. Fill all mandatory fields <br> 3. Click on continue | 1. Request is denied <br> 2. User won't be redirected to the shipping address section <br> 3. validation error message indicating the postal code / Zip field is required |
| **TC-FUNINV-11** | Leave phone number empty | High | Billing fields loaded | 1. Leave the phone number field empty <br> 2. Fill all mandatory fields<br> 3. Click on continue | 1. Request is denied <br> 2. User won't be redirected to the shipping address section <br> 3. validation error message indicating the phone number field is required |

---

# Edge & SEC “Billing Addresses”

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| --- | --- | --- | --- | --- | --- |
| **TC-Edge-01** | Validate spam clicking on continue button | medium | 1. Billing Address fields loaded | 1. Fill all required fields <br> 2. Spam click on the continue button | 1. no crash <br> 2. Every click won't make any effect <br> 3. User is redirected to the shipping address |
| **TC-Edge-02** | Validate copy and paste data | low | 1. Billing Address fields loaded | 1. Navigate to the note app <br> 2. Copy data <br> 3. Navigate to the store checkout page <br> 4. Paste each field with its data | 1. no crash <br> 2. the data is placed and appears inside the fields without problems |
| **TC-Edge-03** | Validate using trailing or  leading spaces | low | 1. Billing Address fields loaded | 1. Enter data in each field with a trailing/leading space <br> 2. Observe the field's validation error message <br> 3. Click on the continue button | 1. no crash <br> 2. A correct error message appears in the restricted fields / System will deal with the space properly and ignore the space |
| **TC-SEC-01** | Validate using SQL injection ( OR ‘1’=’1’) inside the email field | high | 1. Billing address fields loaded | 1. Fill the email field with -> OR '1'='1' <br> 2. Fill all mandatory fields <br> 3. Click on the continue button | 1. no crash <br> 2. System won't execute the code <br> 3. A validation error message appears in the email field <br> 4. No other user's account information is leaked. |
| **TC-SEC-02** | Validate using JavaScript code inside first/last name fields | high | 1. Billing address fields loaded | 1. Fill the first/last name field with -> <script>alert"(hack)"<script> <br> 2. Fill all mandatory fields <br> 3. Click on the continue button | 1. no crash <br> 2. System won't execute the code <br> 3. A validation error message appears in the email field <br> 4. No Pop-ups appear|

---


# Functional Positive “Shipping Address”

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| --- | --- | --- | --- | --- | --- |
| **TC-FUNV-01** | Using valid shipping address information  | High | Shipping Address fields loaded | 1. Fill all mandatory fields <br> 2. Click on continue | 1. No validation error <br> 2. user is redirected to the Shipping Method section |
| **TC-FUNV-02** | Validate leaving optional fields empty | low | Shipping Address fields loaded | 1. Fill all mandatory fields <br> 2. Leave all unmarked/optional fields empty <br> 3. Click on continue | 1. No validation error <br> 2. user is redirected to the Shipping method section |
| **TC-FUNV-03** | Validate the state/province change based on the selected country  | high | Shipping Address field loaded | 1. Select a country <br> 2. Navigate to the state/province drop-down list <br> 3. Observe the options <br> 4. Repeat the procedure for more countries | 1. State/province changes each time the user changes the selected country |

---

# Functional Negative “Shipping Address”
| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| --- | --- | --- | --- | --- | --- |
| **TC-FUNINV-01** | Leaving all mandatory fields empty | High | Shipping address fields loaded | 1. Leave all mandatory fields empty <br> 2. Click on continue | 1. Request denied <br> 2. User remains in the Shipping Address section <br> 3. Validation error message for all mandatory fields | 
| **TC-FUNINV-02** | Selecting state/province without selecting the country | low | Shipping address fields loaded | 1. Do not select the country <br> 2. select the state/province | User not allowed to select the state unless he selects the country |
| **TC-FUNINV-03** | Using wrong fromat email | high | Shipping address fields loaded | 1. make a mistake on the email format <br> 2. fill mandatory fields <br> 3. Click on the continue button | 1. Request is denied <br> 2. User won't be redirected to the shipping method section <br> 3. validation error message indicating the usage of invalid email |
| **TC-FUNINV-04** | Using only spaces in the mandatory fields | medium | Shipping address fields loaded | 1. Fill all mandatory fields with only spaces <br> 2. Click on the continue button | 1. Request is denied <br> 2. User won't be redirected to the shipping method section <br> 3. Validation error message indicating the mandatory field have invalid data |
| **TC-FUNINV-05** | Leave first name empty | high | Shipping address fields loaded | 1. Leave the first name field empty <br> 2. Fill all mandatory fields<br> 3. Click on continue | 1. Request is denied <br> 2. User won't be redirected to the shipping method section <br> 3. validation error message indicating the first name field is required |
| **TC-FUNINV-06** | Leave last name empty | hgh | Shipping address fields loaded | 1. Leave the last name field empty <br> 2. Fill all mandatory fields <br> 3. Click on continue | 1. Request is denied <br> 2. User won't be redirected to the shipping method section <br> 3. validation error message indicating the last name field is required |
| **TC-FUNINV-07** | Leave email empty  | high | Shipping address fields loaded | 1. Leave the email field empty <br> 2. Fill all mandatory fields <br> 3. Click on continue | 1. Request is denied <br> 2. User won't be redirected to the shipping method section <br> 3. validation error message indicating the email field is required |
| **TC-FUNINV-08** | Leave address 1 empty | High | Shipping address fields loaded | 1. Leave the address 1 field empty <br> 2. Fill all mandatory fields <br> 3. Click on continue |  1. Request is denied <br> 2. User won't be redirected to the shipping method section <br> 3. validation error message indicating the address 1 field is required |
| **TC-FUNINV-09** | Leave city empty | High | Shipping address fields loaded | 1. Leave the city field empty <br> 2. Fill all mandatory fields <br> 3. Click on continue | 1. Request is denied <br> 2. User won't be redirected to the shipping method section <br> 3. validation error message indicating the city field is required |
| **TC-FUNINV-10** | Leave postal code / Zip empty | High | Shipping address fields loaded | 1. Leave the postal code/zip field empty <br> 2. Fill all mandatory fields <br> 3. Click on continue | 1. Request is denied <br> 2. User won't be redirected to the shipping method section <br> 3. validation error message indicating the postal code / Zip field is required |
| **TC-FUNINV-11** | Leave phone number empty | High | Shipping address fields loaded | 1. Leave the phone number field empty <br> 2. Fill all mandatory fields<br> 3. Click on continue | 1. Request is denied <br> 2. User won't be redirected to the shipping method section <br> 3. validation error message indicating the phone number field is required |

---

# Edge & SEC “Shipping Addresses”

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| --- | --- | --- | --- | --- | --- |
| **TC-Edge-01** | Validate spam clicking on continue button | medium | 1. Shipping Address fields loaded | 1. Fill all required fields <br> 2. Spam click on the continue button | 1. no crash <br> 2. Every click won't make any effect <br> 3. User is redirected to the shipping method section |
| **TC-Edge-02** | Validate copy and paste data | low | 1. Shipping Address fields loaded | 1. Navigate to the note app <br> 2. Copy data <br> 3. Navigate to the store checkout page <br> 4. Paste each field with its data | 1. no crash <br> 2. the data is placed and appears inside the fields without problems |
| **TC-Edge-03** | Validate using trailing or  leading spaces | low | 1. Shipping Address fields loaded | 1. Enter data in each field with a trailing/leading space <br> 2. Observe the field's validation error message <br> 3. Click on the continue button | 1. no crash <br> 2. A correct error message appears in the restricted fields / System will deal with the space properly and ignore the space |
| **TC-SEC-01** | Validate using SQL injection ( OR ‘1’=’1’) inside the email field | high | 1. Shipping Address fields loaded | 1. Fill the email field with -> OR '1'='1' <br> 2. Fill all mandatory fields <br> 3. Click on the continue button | 1. no crash <br> 2. System won't execute the code <br> 3. A validation error message appears in the email field <br> 4. No other user's account information is leaked. |
| **TC-SEC-02** | Validate using JavaScript code inside first/last name fields | high | 1. Shipping Address fields loaded | 1. Fill the first/last name field with -> <script>alert"(hack)"<script> <br> 2. Fill all mandatory fields <br> 3. Click on the continue button | 1. no crash <br> 2. System won't execute the code <br> 3. A validation error message appears in the email field <br> 4. No Pop-ups appear|

---

# Functional Positive (Shipping Method)
| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| --- | --- | --- | --- | --- | --- |
| **TC-FUNV-01** | Validate selecting land transport as a shipping method | High | 1. Shipping methods loaded | 1. Select Ground/land transport <br> 2. Click on the continue button | 1. User is redirected to the payment method section |
| **TC-FUNV-02** | Validate Selecting Air shipping “one-day” | High | 1. Shipping methods loaded | 1. Select Next day air shipping method <br> 2. Click on the continue button | 1. User is redirected to the payment method section |
| **TC-FUNV-03** | Validate Selecting Air shipping “two-day” | High | 1. Shipping methods loaded | 1. Select 2nd day air shipping method <br> 2. Click on the continue button | 1. User is redirected to the payment method section |

---

 # Functional Negative (Shipping Method)
| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| --- | --- | --- | --- | --- | --- |
| **TC-FUNINV-01** | Validate un-check shipping method | High | 1. Shipping methods loaded | 1. Un-check the shipping method | 1. The radio box can't be unchecked |
