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

---

# UI (Shipping Method)

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| --- | --- | --- | --- | --- | --- |
| **TC-UI-01** | Validate all shipping methods have a radio box | High | 1. Shipping methods loaded | 1. Observe the method's design and layout | 1. All Methods have a radio box |
| **TC-UI-02** | Validate the method selected radio button is checked | High | 1. Shipping methods loaded | 1. Select a method <br> 2. Observe the selected method's radio box state | 1. The selected method's radio box is checked |
| **TC-UI-03** | Validate the shipping method elements alignment | High | 1. Shipping methods loaded | 1. Observe the alignment of the shipping methods | 1. No overlapping between the methods |

---

# Functional Positive (Payment Method)

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| --- | --- | --- | --- | --- | --- |
| **TC-FUNV-01** | Validate choosing pay by cheque or money order | High | 1. The user completed the shipping method section <br> 2. Payment methods loaded | 1. Select pay by cheque or money order <br> 2. Click on the continue button | 1. The user is redirected to the payment information page <br> 2. User won't be asked to enter their credit card information |
| **TC-FUNV-02** | Validate choosing pay with credit card | High | 1. The user completed the shipping method section <br> 2. Payment methods loaded | 1. Select pay by credit card <br> 2. Click on the continue button | 1. The user is redirected to the payment information page <br> 2. User will be asked to enter their credit card information |

---

Functional Negative (Payment Method)

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| --- | --- | --- | --- | --- | --- |
| **TC-FUNV-01** | Validate unselect payment method empty | High | 1. The user completed the shipping method section <br> 2. Payment methods loaded | 1. Unselect payment method | User is obligated to choose a method |

---

# UI (Payment Method)

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| --- | --- | --- | --- | --- | --- |
| **TC-UI-01** | Validate all payment methods have a radio box | High | 1. Payment methods loaded | 1. Observe the method's design and layout | 1. All Methods have a radio box |
| **TC-UI-02** | Validate the method selected radio button is checked | High | 1. Payment methods loaded | 1. Select a method <br> 2. Observe the selected method's radio box state | 1. The selected method's radio box is checked |
| **TC-UI-03** | Validate the payment method elements alignment | High | 1. Payment methods loaded | 1. Observe the alignment of the payment methods | 1. No overlapping between the methods |

---

# Functional positive (payment information-Credit card)

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| --- | --- | --- | --- | --- | --- |
| **TC-FUNV-01** | Validate using visa for credit card information | High | 1. User chose a credit card as a payment method <br> 2. Payment information fields loaded | 1. Select Visa card type <br> 2. Fill all fields <br> 3. Click on the continue button | 1. User is redirected to confirm order section <br> 2. Data saved in the database |
| **TC-FUNV-02** | Validate using Master card | High | 1. User chose a credit card as a payment method <br> 2. Payment information fields loaded | 1. Select Master card type <br> 2. Fill all fields <br> 3. Click on the continue button | 1. User is redirected to confirm order section <br> 2. Data saved in the database |
| **TC-FUNV-03** | Validate using Discover | High | 1. User chose a credit card as a payment method <br> 2. Payment information fields loaded | 1. Select Discover type <br> 2. Fill all fields <br> 3. Click on the continue button | 1. User is redirected to confirm order section <br> 2. Data saved in the database |
| **TC-FUNV-04** | Validate using Amex | High | 1. User chose a credit card as a payment method <br> 2. Payment information fields loaded | 1. Select Amex type <br> 2. Fill all fields <br> 3. Click on the continue button | 1. User is redirected to confirm order section <br> 2. Data saved in the database |

---

# Functional Negative (payment information-Credit card)

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| --- | --- | --- | --- | --- | --- |
| **TC-FUNINV-01** | Validate leaving all fields empty | High | 1. User chose a credit card as a payment method <br> 2. Payment information fields loaded | 1. Leave all fields empty <br> 2. Click on the continue button | 1. Validation error message indicating fields required |
| **TC-FUNINV-02** | Validate selecting wrong credit card type | High | 1. User chose a credit card as a payment method <br> 2. Payment information fields loaded | 1.Select a card type that is not attached to the given data <br> 2. Click on the continue button | 1. Validation error message indicating invaild data |
| **TC-FUNINV-03** | Validate leaving cardholder name empty | High | 1. User chose a credit card as a payment method <br> 2. Payment information fields loaded | 1. Leave Cardholder name field empty <br> 2. Click on the continue button | 1. Validation error message indicating cardholder name is required <br> 2. User is not redirected to the confirm section |
| **TC-FUNINV-04** | Validate leaving card number field empty | High | 1. User chose a credit card as a payment method <br> 2. Payment information fields loaded | 1. Leave card number field empty <br> 2. Click on the continue button | 1. Validation error message indicating card number is required <br> 2. User is not redirected to the confirm section |
| **TC-FUNINV-05** | Validate leaving the card code empty | High | 1. User chose a credit card as a payment method <br> 2. Payment information fields loaded | 1. Leave card code field empty <br> 2. Click on the continue button | 1. Validation error message indicating card code is required <br> 2. User is not redirected to the confirm section |
| **TC-FUNINV-06** | Validate selecting expired date  | High | 1. User chose a credit card as a payment method <br> 2. Payment information fields loaded | 1. Select an expired date <br> 2. Click on the continue button | 1. Validation error message indicating that the card is expired <br> 2. User is not redirected to the confirm section |
---

# UI (payment information-Credit card)

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| --- | --- | --- | --- | --- | --- |
| **TC-UI-01** | Verify Credit Card section is displayed when user selects Credit Card | High | 1. Payment information fields loaded | 1. Select "Credit Card" payment method <br> 2. Click on the continue button | 1. Select credit card dropdown displayed <br> 2. Cardholder name field displayed <br> 3. Card number field displayed <br> 4. Expiration date dropdowns displayed <br> 5. Card code field displayed <br> 6. Cheque instructions text NOT displayed |
| **TC-UI-02** | Verify the Cheque section is displayed when the user selects Pay by Cheque | High | 1. Payment information fields loaded | 1. Select "Pay by Cheque" <br> 2. Click on the continue button | 1. Company name and address displayed <br> 2. Instruction text displayed <br> 3. Credit card fields NOT displayed |
| **TC-UI-03** | Verify switching between payment methods updates UI dynamically | High | 1. Payment information fields loaded | 1. Select Credit Card <br> 2. Switch to Cheque <br> 3. Switch back to Credit Card | 1. UI updates correctly each time <br> 2. correctly No overlapping sections <br> 3. No broken layout <br> 4. No console errors |

---

# Edge & Security (payment information-Credit card)

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| --- | --- | --- | --- | --- | --- |
| **TC-Edge-01** | Validate Enter a too long card holder name  | low | 1. Payment information fields loaded | 1. Fill the cardholder name field with a too-long name <br> 2. Fill all required fields <br> 3. click on the continue button |  |
| **TC-Edge-02** | Validate using spaces in the card information fields | low | 1. Payment information fields loaded | 1. Fill fields with spaces <br> 2. click on continue | 1. no crash <br> 2. the system should deal properly with the spaces by deleting them/system will prevent the user from continuing |
| **TC-SEC-01** | Validate using SQL injection ( OR ‘1’=’1’) inside the cardholder name field | high | 1. Payment information fields loaded | 1. Fill the cardholder name field with -> OR '1'='1' <br> 2. Fill all mandatory fields <br> 3. Click on the continue button | 1. no crash <br> 2. System won't execute the code <br> 3. A validation error message appears in the cardholder name field <br> 4. No other user's account information is leaked. |
| **TC-SEC-02** | Validate using JavaScript code inside card number field | high | 1. Payment information fields loaded | 1. Fill the card number field with -> <script>alert"(hack)"<script> <br> 2. Fill all mandatory fields <br> 3. Click on the continue button | 1. no crash <br> 2. System won't execute the code <br> 3. A validation error message appears in the card number field <br> 4. No Pop-ups appear |

---

# Performance Global

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| --- | --- | --- | --- | --- | --- |
| **TC-PFM-01** | Validate all sections continue button response time | High | Checkout page laoded | 1. Click on the continue button for every section <br> 2. Observe the response time | 1. User has to be redirected to the next section within < 3s |
| **TC-PFM-02** | Validate error message notification time | Medium | Checkout page laoded | 1. Navigate to any section <br> 2. Leave a mandatory field empty <br> 3. Click on the continue button <br> 4. Observe the error message time show up | 1. The message has to be loaded immediately after the page is loaded |

---

# Edge Global

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| --- | --- | --- | --- | --- | --- |
| **TC-Edge-01** | Validate page functionality when user is using the store with 3G throttling connection | High | 1. User is having #G throttling connection <br> 2. Checkout page loaded | 1. Navigate to the Billing Address section <br> 2. Complete the form <br> 3. Click on the continue button | 1. Page works correctly <br> 2. No crash <br> 3. page design and layout is consistent |

---

# UI Global

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| --- | --- | --- | --- | --- | --- |
| **TC-UI-01** | Validate error message in the right place | High | Checkout page loaded | 1. Leave a mandatory field empty <br> 2. Click on the continue button <br> 3. Observe the error message place | Error message shall appear near the field with invalid data |
| **TC-UI-02** | Validate error message text style | High | Checkout page loaded | 1. Leave a mandatory field empty <br> 2. Click on the continue button <br> 3. Observe the error message style | Error message color is red |
| **TC-UI-03** | Validate fields state when it is active | low | Checkout page loaded | 1. Navigate to any field in any section <br> 3. Observe the field state | 1. Writing cursor is placed inside the field <br> 2. Field outline highlight color changes |
| **TC-UI-04** | Validate alignment of all sections elements | High | Checkout page loaded | 1. Observe the sections' fields alignment | All fields are aligned correctly without any overlap |
| **TC-UI-05** | Validate buttons state when hovering on them | low | Checkout page loaded | 1. Hover over any button <br> 2. Observe the button state | Button color changes |
| **TC-UI-06** | Validate consistent font styles | High | Checkout page loaded | 1. Observe font style across the page | All texts have the same color and size, and type|

---

# Usability Global

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| --- | --- | --- | --- | --- | --- |
| **TC-USB-01** | Validate using the keyboard navigation keys to move forward and backward | low | Checkout page loaded | 1. Click on the tab button <br> 2. Observe the focus <br> 3. Click on the tab + shift buttons <br> 4. Observe the focus | 1. Focus moves to the next field when clicking on the tab button <br> 2. Focus moving to the previous field when clicking on tab + shift |
| **TC-USB-02** | Validate the page can be read via the screen reading apps | High | Checkout page loaded | 1. Open the screen reader <br> 2. Scroll through the page | 1. The app should read every text on the page <br> 2. The app can read images' alt text |
| **TC-USB-03** | Field’s suggestion input | low | Checkout page loaded | 1. Click inside any field  | 1. Suggestion input will appear from previous usage <br> 2. User can select the suggestion |
