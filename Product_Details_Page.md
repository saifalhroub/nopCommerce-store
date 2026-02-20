# Feature: <Feature Name>

---

# 1️⃣ User Story
As a user,  
I want a product details page,  
So I can get a deeper understanding of the product.

As a user,
I want a category's products page,
So I can see the available products

 

---

# 2️⃣ Acceptance Criteria (BDD)

## AC1 – 
Given the user is on the product page
When the user clicks on the product image
Then the user will be redirected to the product details page

## AC2 – 
Given the user is using the store
When the user is on the product details page
Then the product details will appear:
 - Product name
 - Product image
 - Product description
 - Product price
 - Review rating

## AC3 – 
Given the user is using the store
When the user is on the product details page
Then the user will be able to add the product to the cart using add to cart button
And a quantity field will be available to determine the number of copies wanted

## AC4 -
Given the user is using the store
When the user is on product details page
Then the user will be asked to select the shipping destination

## AC5 - 
Given the user is on the product details page
When the user is on a product is available for renting
Then the user will be asked to select the renting date

## AC6 - 
Given the user is on the product details page
When the product is a gift card product
Then the user will be asked to fill in:
 - Recipient name (Mandatory)
 - Customer name (Mandatory)
 - Message (Optional)

## AC7 - 
Given the user is using the app 
When the user is on Build your own pc product details page
Then the user will be asked to select:
 - Processor (Mandatory)
 - RAM (Mandatory)
 - HDD (Mandatory)
 - OS (Mandatory)
 - Software (Optional)

## AC8 -
Given the user is using the store
When the user is on the product details page 
Then the user will be able to add the product to the wishlist

## AC9 -
Given the user is using the store
When the user is on the product details page 
Then the user will be able to add the product to the compare list

## AC10 -
Given the user is using the store
When the user is on the product details page 
Then the user will be able to email and share the product via email with a friend 

## AC11 -
Given the user is using the store
When the user is on the product details page 
Then the user will be able to see related products 

## AC12 -
Given the user is using the store
When the user is on the product details page 
Then the user will be able to see others' reviews

## AC13 -
Given the user is using the store
When the user is on the shoe detail page
Then the user will be asked to select: - shoe color. - shoe size
---

# 3️⃣ Test Cases

---

## Functional – Valid Scenarios

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-FUNCV-01 | Validate adding one product to cart | High | User is on product details page |

**Steps:**
1. Click on the add to cart button
   

**Expected Result:**
-  A confirmation message will show up
-  The total number appears beside the add to cart link change accordingly
-  Only one item will be added

---

| TC-FUNCV-02 | Validate the number of items to be add functionality | High | User is on product details page |

**Steps:**
1. Type in a positive number
2. Click on add to cart
   

**Expected Result:**
-  A confirmation message will show up
-  The total number appear beside the add to cart link will change accordingly
  
---

| TC-FUNCV-03 | Validate renting a product | High | User is on product details page |

**Steps:**
1. Select the number of the product you want
2. Fill in the start date with a valid date
3. Fill in the End date with a valid date that lies after the start date
4. Click on the Rent button 
   

**Expected Result:**
-  A confirmation message will show up
-  The total number appear beside the add to cart link will change accordingly
-  The product will be added to the Cart
  
---

| TC-FUNCV-04 | Validate adding a product to the wishlist | medium | User is on product details page |

**Steps:**
1. Click on the add to Wishlist button
   

**Expected Result:**
-  A confirmation message will show up
-  The total number that appears beside the wishlist link will change accordingly
-  The product will be added to the Wishlist
  
---

| TC-FUNCV-05 | Validate adding a product to the compare list | medium | User is on product details page |

**Steps:**
1. Click on the add to Compare List button
   

**Expected Result:**
-  A confirmation message will show upص
-  The product will be added to the Compare list  
---

| TC-FUNCV-06 | Validate building your own pc | High | User is on product details page |

**Steps:**
1. Select all mandatory options
2. Click on the add to Cart button
   

**Expected Result:**
-  A confirmation message will show up
-  The product will be added to the Cart
---

| TC-FUNCV-07 | Validate selecting a shipping destination | High | User is on product details page |

**Steps:**
1. Fill all mandatory fields with valid data
2. Click on the Apply button
3. Select the shipping method
   

**Expected Result:**
-  A shipping destination and price will show up 
---

| TC-FUNCV-08 | Validate leaving a review for a product while logged in | low | User is on product details page |

**Steps:**
1. Navigate to any product details page
2. Fill all mandatory fields with valid data
3. Click on the Submit Review button
   
**Expected Result:**
-  A confirmation message will show up: "Product review is successfully added."
-  The Review will appear in the Existing reviews section and contains:
   - Review Title
   - Rating bar
   - Review text
   - Reviewer name
   - Date and time of publishing 
---

| TC-FUNCV-09 | Validate adding to the cart a shoe with its color and size  | hig | User is on the shoe details page |

**Steps:**
1. Select the shoe color
2. Select the shoe size
3. Click on add to cart button
   
**Expected Result:**
-  A confirmation message will show up
-  The total number appear beside the add to cart link will change accordingly
-  The product will be added to the Cart
---

| TC-FUNCV-10 | Validate product total price that depends on the quantity "Offer" | high | User is on others section inside electronics |

**Steps:**
1. Navigate to Beats Pill Wireless Speaker
2. Add the quantity that matches the offer
3. Click on add to cart button
4. Navigate to the cart page
5. Observe the price
   
**Expected Result:**
-  A confirmation message will show up
-  The total number appear beside the add to cart link will change accordingly
-  The products will be added to the Cart
-  The total price of the selected product matches the offer
---

| TC-FUNCV-11 | Validate selecting size for cloths | high | User is on the clothes |

**Steps:**
1. Select a subcategory
2. Select item
3. Select size
4. Repeat the steps for all items
   
**Expected Result:**
-  The user can select the available sizes
  
---

| TC-FUNCV-12 | Validate using valid data to send card gift | high | User is on the gift card |

**Steps:**
1. Fill in all fields with valid data
2. detern=mine the quantity
3. Click on the Add to Cart button
   
**Expected Result:**
-  A confirmation message will show up
-  The total number that appears beside the add to cart link will change accordingly
-  The products will be added to the Cart
-   

---

## Functional – Invalid Scenarios

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-FUNCINV-01 | Validate adding to (Cart/Wishlist/Compare list) functionalities to no internet connection | High | User is on product details page |

**Steps:**
1. Cut off your internet connection
2. Add a product to (Cart/Wishlist/Compare list)

**Expected Result:**
- No product is added to any of (Cart/Wishlist/Compare list)
- A clear error message telling user: "Please connect to the internet"

---


| TC-FUNCINV-03 | Validate leaving rent fields empty | High | User is on product details page |

**Steps:**
1. Leave the start and end date empty
2. Click on the Rent button
   
**Expected Result:**
- An error message will appear telling the user: "Enter rental start date."
- No product is added to the cart

---

| TC-FUNCINV-04 | Validate leaving start renting date empty | High | User is on product details page |

**Steps:**
1. Leave the start date empty
2. Click on the Rent button
   
**Expected Result:**
- An error message will appear telling the user: "Enter rental start date."
- No product is added to the cart

---

| TC-FUNCINV-05 | Validate leaving end renting date empty | High | User is on product details page |

**Steps:**
1. Leave the end date empty
2. Click on the Rent button
   
**Expected Result:**
- An error message will appear telling the user: "Enter rental end date."
- No product is added to the cart

---

| TC-FUNCINV-06 | Validate leaving all mandatory pc components fields empty while building your own pc | High | User is on product details page |

و**Steps:**
1. Leave all mandatory fields empty
2. Click on the add to cart button
   
**Expected Result:**
- An error message will appear telling the user: "Please select (......)."
- No product is added to the cart

---
| TC-FUNCINV-07 | Validate leaving processor field empty while building your own pc | High | User is on build your own pc details page |

**Steps:**
1. Leave the processor field empty
2. Click on the add to cart button
   
**Expected Result:**
- An error message will appear telling the user: "Please select Processor."
- No product is added to the cart

---

| TC-FUNCINV-08 | Validate leaving Ram field empty while building your own pc | High | User is on build your own pc details page |

**Steps:**
1. Leave the Ram field empty
2. Click on the add to cart button
   
**Expected Result:**
- An error message will appear telling the user: "Please select RAM."
- No product is added to the cart

---

| TC-FUNCINV-09 | Validate leaving HDD field empty while building your own pc | High | User is on build your own pc details page |

**Steps:**
1. Leave the HDD field empty
2. Click on the add to cart button
   
**Expected Result:**
- An error message will appear telling the user: "Please select HDD."
- No product is added to the cart

---

| TC-FUNCINV-10 | Validate leaving all mandatory shoes fields empty | High | User is on product details page |

**Steps:**
1. Leave all mandatory fields empty
2. Click on the add to cart button
   
**Expected Result:**
- An error message will appear telling the user: "Please select (......)."
- No product is added to the cart

---

| TC-FUNCINV-11 | Validate leaving shoes color field empty | High | User is on product details page |

**Steps:**
1. Select shoes color
2. Leave shoes size empty
3. Click on the add to cart button
   
**Expected Result:**
- An error message will appear telling the user: "Please select the shoe size."
- No product is added to the cart

---

| TC-FUNCINV-12 | Validate leaving shoes size field empty | High | User is on product details page |

**Steps:**
1. Select shoes size
2. Leave shoes color empty
3. Click on the add to cart button
   
**Expected Result:**
- An error message will appear telling the user: "Please select the shoe color."
- No product is added to the cart

---

| TC-FUNCINV-13 | Validate leaving text field empty on the Customed T-shirt page | High | User is on Custom T-shirt page |

**Steps:**
1. Select the shoe size
2. Leave the shoe color empty
3. Click on the add to cart button
   
**Expected Result:**
- An error message will appear telling the user: "Please select the shoe color."
- No product is added to the cart

---

| TC-FUNCINV-14 | Validate leaving Gift Card mandatory fields empty | High | User is on Gift Card page |

**Steps:**
1. Leave all mandatory fields empty
3. Click on the add to cart button
   
**Expected Result:**
- An error message will appear telling the user: "Enter a valid value for the mandatory fields."
- No product is added to the cart

---

| TC-FUNCINV-15 | Validate leaving Gift Card Recipient's Name field empty | High | User is on the Recipient's Name page |

**Steps:**
1. Leave the Recipient's Name field empty
2. Fill all other mandatory fields with valid data
3. Click on the add to cart button
   
**Expected Result:**
- An error message will appear telling the user: "Enter a valid Recipient's Name."
- No product is added to the cart

---

| TC-FUNCINV-17 | Validate leaving Gift Card Recipient's Email field empty | High | User is on the Recipient's Email page |

**Steps:**
1. Leave the Recipient's Email field empty
2. Fill all other mandatory fields with valid data
3. Click on the add to cart button
   
**Expected Result:**
- An error message will appear telling the user: "Enter a valid Recipient's Email."
- No product is added to the cart

---

| TC-FUNCINV-18 | Validate leaving Gift Card Your Name field empty | High | User is on the Your Name page |

**Steps:**
1. Leave the Your Name field empty
2. Fill all other mandatory fields with valid data
3. Click on the add to cart button
   
**Expected Result:**
- An error message will appear telling the user: "Enter a valid Your Name."
- No product is added to the cart

---

| TC-FUNCINV-19 | Validate leaving Gift Card Your Email field empty | High | User is on the Your Email page |

**Steps:**
1. Leave the Your Email field empty
2. Fill all other mandatory fields with valid data
3. Click on the add to cart button
   
**Expected Result:**
- An error message will appear telling the user: "Enter a valid Your Email field."
- No product is added to the cart

---

## Boundary Value Testing

| TC-BVA-01 | Validate adding the maximum allowed number of the same product | High | User is on product details page |

**Steps:**
1. Fill in the number of copies that you want (9999)
2. Click on the add to Cart button
   

**Expected Result:**
-  A confirmation message will show up: (The product has been added to your shopping cart)
-  All of the product copies will be added to the Cart
---

| TC-BVA-02 | Validate adding the minimum allowed number of the same product | High | User is on product details page |

**Steps:**
1. Fill in the number of copies that you want (1)
2. Click on the add to Cart button
   

**Expected Result:**
-  A confirmation message will show up: (The product has been added to your shopping cart)
-  All of the product copies will be added to the Cart
---

| TC-BVA-03 | Validate adding a zero copies of a product less than the min allowed 1| High | User is on product details page |

**Steps:**
1. Fill in the number of copies that you want (0)
2. Click on the add to Cart button
   

**Expected Result:**
-  A validation message will appear saying: "Quantity should be positive."
-  No product will be added to the cart
-  No crashes will happen to the system
---

| TC-BVA-04 | Validate adding 10000 copies of a product more than the max allowed 9999 | High | User is on product details page |

**Steps:**
1. Fill in the number of copies that you want (10000)
2. Click on the add to Cart button
   

**Expected Result:**
-  A validation message will appear saying: "The maximum quantity allowed for purchase is 10000."
-  No product will be added to the cart
-  No crashes will happen to the system

---
## Edge Cases


| TC-EDGE-01 | Validate write the number in letters | low | User is on product details page |

**Steps:**
1. Fill the quantity field with a number in letters
2. Click on the add to the cart button
   
**Expected Result:**
- No product is added to the Cart
- A clear error message telling the user: "Quantity should be positive"

---


| TC-EDGE-02 | Validate writting a special character in the quantity field | low | User is on product details page |

**Steps:**
1. Fill the quantity field with a number in letters
2. Click on the add to the cart button
   
**Expected Result:**
- No product is added to the Cart
- A clear error message telling the user: "Quantity should be positive."

---

| TC-EDGE-03 | Validate using capital letters in  Email fields | low | User is on Gift Card details page |

**Steps:**
1. Fill the Recipient Email/Your email with capital letters
2. Fill all mandatory fields
3. Click on the add to the cart button
   
**Expected Result:**
- The system ignores the letter state
- The system accepts the add to cart request
- Product is added to the cart
- No crashes to the system occur
---

| TC-EDGE-03 | Validate using space in  Email fields | low | User is on Gift Card details page |

**Steps:**
1. Fill the Recipient Email/Your email with a leading/trailing space
2. Fill all mandatory fields
3. Click on the add to the cart button
   
**Expected Result:**
- The system ignores the spaces
- The system accepts the add to cart request
- Product is added to the cart
- No crashes to the system occur
---

| TC-EDGE-04 | Validate using space in quantity field | medium | User is on any product details page |

**Steps:**
1. Fill the quantity field with a trailing space
2. Fill all mandatory fields
3. Click on the add to the cart button
   
**Expected Result:**
- The system rejects the add to cart request
- Product is not added to the cart
- A validation error message that says: (Quantity should be positive)
---



| TC-EDGE-06 | Validate selecting a too far end date for a rental product | medium | User is on the Elegant Gemstone Necklace (rental) page |

**Steps:**
1. Select the start date
2. Select a too far end date
3. Click on the add to Cart button
   
**Expected Result:**
- The system accepts the add to cart request
- Product is added to the cart
- No crashes to the system occur

---

| TC-EDGE-07 | Validate using emojis inside the message field for the gift card product | medium | User is on the Gift Card page |

**Steps:**
1. Fill in the message field with emojis
2. Fill all mandatory fields
   
**Expected Result:**


---
## Security Testing

| TC-SEC-01 | Validate adding a negative number for the product quantity | High | User is on product details page |

**Steps:**
1. Fill the quantity field with a negative number
2. Click on the add to Cart button
   
**Expected Result:**
- No product is added to the Cart
- A clear error message telling the user: "Quantity should be positive."

---

| TC-SEC-02 | Validate adding a decimal number (1.5) for the product quantity | High | User is on product details page |

**Steps:**
1. Fill the quantity field with a decimal number (1.5)
2. Click on the add to Cart button
   
**Expected Result:**
- No product is added to the Cart
- A clear error message telling the user: "Quantity should be positive."

---
| TC-SEC-03 | Validate using javascript code inside (Name/Message/Text on shirt) | High | User is on the product details page that contains (Name/Message/Text on shirt) |

**Steps:**
1. Fill the (Name/Message/Text on shirt) fields with: <script>alert('Hacked')</script>
2. Click on the add to Cart button
   
**Expected Result:**

---

| TC-SEC-04 | Validate using a five million character in the (Name/Message/Text on shirt) field | low | User is on the product details page that contains (Name/Message/Text on shirt) |

**Steps:**
1. Fill the message field with a1 million character
2. Fill all mandatory fields
3. Click on the add to the cart button
   
**Expected Result:**
- The system accepts the add to cart request
- Product is added to the cart
- No crashes to the system occur

---

| TC-SEC-05 | Validate select a rental end date that lies before the start rental date | High | User is on rental product page |

**Steps:**
1. Select a start date 25/2
2. Select an end date 24/2
   
**Expected Result:**
- No product is added to the Cart
- A clear error message telling the user: "Rental start date should be less than end date."

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

----------------------------------------------------------------------------------------------------------------------------------------------------------------

# 🚀 Ultimate Test Documentation: E-Commerce Store
**Project:** nopCommerce Customization Testing  
**Scope:** Product Details, Rental, Gift Cards, and Build-Your-Own-PC.

---

## 1️⃣ User Stories & Acceptance Criteria (BDD)

### **Story 1: Product Interaction**
> **As a user,**
> I want to view and manage product selections,  
> **So that** I can make informed purchases.

* **AC1 (Navigation):**
   Given the user is on the category page
   When they click a product
   Then they are redirected to the correct Details Page.
  
* **AC2 (Add to Cart):**
  Given valid inputs
   When "Add to Cart" is clicked
   Then a confirmation appears
   and the cart counter increments.
  
* **AC3 (Wishlist/Compare):**
  User can add items to Wishlist or Compare list without duplicates.

### **Story 2: Complex Products (Rental/Gift/PC)**
> **As a user**
> I want to customize specific product types (Rental, Gift Card, PC),  
> **So that** the product meets my exact needs.

* **AC4 (Rental):**
   End Date must be later than Start Date.
  
* **AC5 (Gift Card):**
  Recipient and Sender names/emails are mandatory and must be validated.
  
* **AC6 (Custom PC):**
   All mandatory components (CPU, RAM, HDD) must be selected before adding to cart.

---

## 2️⃣ Functional Test Cases (Happy Path)

| TC ID | Title | Priority | Pre-conditions | Steps | Expected Result |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TC-FUNC-01** | Add Single Item | **High** | Product page loaded | 1. Click "Add to Cart" | Success msg; Counter +1. |
| **TC-FUNC-02** | Add Multiple Qty | **High** | Product page loaded | 1. Enter Qty = 5 <br> 2. Click Add | Success msg; 5 units in cart. |
| **TC-FUNC-03** | Valid Rental | **High** | Rental product page | 1. Select Start (Today) <br> 2. Select End (Tomorrow) | Product added with dates saved. |
| **TC-FUNC-04** | Build PC (Complete) | **High** | PC Product page | 1. Select all mandatory components <br> 2. Click Add | Product added with config. |
| **TC-FUNC-05** | Gift Card (Full Data) | **Medium** | Gift Card page | 1. Fill all fields (Valid) <br> 2. Click Add | Success; Data stored correctly. |

---

## 3️⃣ Negative & Boundary Testing (Error Handling)

| TC ID | Title | Priority | Input Data | Expected Result |
| :--- | :--- | :--- | :--- | :--- |
| **TC-NEG-01** | No Internet | **High** | Disable Network | Clear error: "Check your connection". |
| **TC-NEG-02** | Invalid Rental Logic | **High** | End Date < Start Date | Error: "End date must be after Start". |
| **TC-BVA-01** | Quantity Zero | **Medium** | Qty = 0 | Error: "Quantity must be positive". |
| **TC-BVA-02** | Quantity Max | **Low** | Qty = 10,000 | Validation error: "Max limit reached". |
| **TC-NEG-03** | Missing PC Parts | **High** | Leave RAM empty | Specific error: "Please select RAM". |

---

## 4️⃣ Security & Edge Case Testing

| TC ID | Title | Type | Input / Scenario | Expected Result |
| :--- | :--- | :--- | :--- | :--- |

| **TC-SEC-01** | **XSS Attack** | Security | `<script>alert('Hacked')</script>` | Input is sanitized/rendered as text. |

| **TC-SEC-02** | **SQL Injection** | Security | `' OR 1=1 --` | System rejects or treats as raw text. |

| **TC-SEC-03** | **Price Manipulation** | Security | Qty = `-5` | System blocks; No price deduction. |

| **TC-EDGE-01** | Emoji Support | Edge | 🚀🔥 in Gift Message | System accepts and displays correctly. |

| **TC-EDGE-02** | Email Sanitization | Edge | ` user@test.com ` (spaces) | Spaces trimmed; Email accepted. |

| **TC-SEC-04** | Overload Input | Security | 1,000,000 characters | System truncates or rejects; No crash. |

---

# 5️⃣ Global & Non-Functional Testing

---

# A. Usability & UI Testing 🎨

---

## TC-UI-01 – Mandatory Field Indicator

**Preconditions:**  
User is on a page containing mandatory fields (e.g., Gift Card).

**Steps:**
1. Navigate to page.
2. Visually inspect mandatory fields.
3. Inspect HTML attributes.

**Expected Result:**
- Red asterisk (*) appears clearly next to required fields.
- `aria-required="true"` is present.
- Screen readers announce field as required.

---

## TC-UI-02 – Keyboard Navigation Order

**Preconditions:**  
User is on Product Details page.

**Steps:**
1. Press `TAB` repeatedly.
2. Observe focus order.

**Expected Result:**
- Focus moves logically:
  Header → Image → Details → Quantity → Add to Cart → Wishlist → Footer.
- No focus trap.

---

## TC-UI-03 – Focus Visibility

**Preconditions:**  
User navigates using keyboard.

**Steps:**
1. Navigate using `TAB`.
2. Observe focused element.

**Expected Result:**
- Visible focus indicator (outline/highlight) appears on every interactive element.

---

## TC-UI-04 – Error Message Clarity & Placement

**Preconditions:**  
User triggers validation error.

**Steps:**
1. Submit empty mandatory form.
2. Observe error message.

**Expected Result:**
- Error appears near relevant field.
- Message is clear and descriptive.
- Uses distinct color (e.g., red).

---

## TC-UI-05 – Responsive – Mobile

**Preconditions:**  
Product page opened in mobile viewport.

**Steps:**
1. Set viewport to 375x667.
2. Verify layout.

**Expected Result:**
- No horizontal scroll.
- Buttons ≥ 44x44px.
- Images scale properly.
- Text readable.

---

## TC-UI-06 – Responsive – Tablet

**Preconditions:**  
Tablet viewport.

**Steps:**
1. Set viewport to 768x1024.
2. Verify layout.

**Expected Result:**
- Layout adapts properly.
- 2-column grid or optimized tablet layout.

---

## TC-UI-07 – Responsive – Desktop

**Preconditions:**  
Desktop viewport.

**Steps:**
1. Set viewport to 1920x1080.
2. Verify spacing and alignment.

**Expected Result:**
- Layout uses space efficiently.
- No excessive stretching.
- Content centered or max-width applied.

---

## TC-UI-08 – Button States

**Preconditions:**  
User is on any interactive page.

**Steps:**
1. Hover over button.
2. Click and hold.
3. Disable internet and attempt action.

**Expected Result:**
- Distinct hover / active / disabled states.
- Disabled state clearly prevents action.

---

# B. Compatibility Testing 🌐

---

## TC-COMP-01 – Cross-Browser – Chrome

**Environment:** Chrome 120+ (Windows 11)

**Expected Result:**
- All features work as baseline.
- No layout or JavaScript errors.

---

## TC-COMP-02 – Cross-Browser – Firefox

**Environment:** Firefox 122+ (Windows 11)

**Expected Result:**
- Same behavior as Chrome baseline.
- No console errors.

---

## TC-COMP-03 – Cross-Browser – Safari

**Environment:** Safari 17+ (macOS)

**Expected Result:**
- No rendering issues (Flexbox / Grid).
- Layout matches baseline behavior.

---

## TC-COMP-04 – Cross-Browser – Edge

**Environment:** Edge 120+ (Windows 11)

**Expected Result:**
- Same functional behavior as baseline.

---

## TC-COMP-05 – Mobile – iOS Safari

**Environment:** iPhone 13 / iOS 17

**Expected Result:**
- Touch targets ≥ 44x44px.
- No layout breakage.
- Smooth interaction.

---

## TC-COMP-06 – Mobile – Android Chrome

**Environment:** Android 14 / Chrome

**Expected Result:**
- Same as iOS baseline behavior.

---

## TC-COMP-07 – Tablet – iPadOS Safari

**Environment:** iPadOS 17

**Expected Result:**
- Tablet optimized layout.
- No content cutoff.

---

## TC-COMP-08 – OS – Windows Scaling

**Environment:** Windows 10 / 11 (100%, 125%, 150%)

**Expected Result:**
- UI scales correctly.
- No overlap or clipping.

---

## TC-COMP-09 – OS – macOS

**Environment:** macOS Ventura / Sonoma

**Expected Result:**
- Text rendering is clear.
- No unexpected boldness or blur.

---

# C. API Testing (Backend) ⚙️

---

## TC-API-01 – Valid Simple Product

**Endpoint:** `POST /add-to-cart`  
**Payload:** `{ "productId": 1, "quantity": 2 }`  
**Expected Status:** 200 OK  

**Expected Result:**
- Success response.
- Cart count updated.
- Database shows correct quantity.

---

## TC-API-02 – Valid Rental Product

**Endpoint:** `POST /add-to-cart`  
**Expected Status:** 200 OK  

**Expected Result:**
- Dates saved correctly.
- Rental stored properly in cart.

---

## TC-API-03 – Valid Gift Card

**Endpoint:** `POST /add-to-cart`  
**Expected Status:** 200 OK  

**Expected Result:**
- All fields stored.
- No data truncation.

---

## TC-API-04 – Valid Custom PC

**Endpoint:** `POST /add-to-cart`  
**Expected Status:** 200 OK  

**Expected Result:**
- Configuration saved.
- Cart reflects selected options.

---

## TC-API-05 – Invalid Product ID

**Expected Status:** 404 Not Found  

**Expected Result:**
- Error: "Product not found".

---

## TC-API-06 – Negative Quantity

**Expected Status:** 400 Bad Request  

**Expected Result:**
- Validation error: "Quantity must be positive".

---

## TC-API-07 – Zero Quantity

**Expected Status:** 400 Bad Request  

**Expected Result:**
- Validation error: "Quantity must be at least 1".

---

## TC-API-08 – Missing Quantity

**Expected Status:** 400 Bad Request  

**Expected Result:**
- Error indicates missing required field.

---

## TC-API-09 – Invalid Rental Dates

**Expected Status:** 400 Bad Request  

**Expected Result:**
- Error: "End date must be after start date".

---

## TC-API-10 – Missing Gift Card Field

**Expected Status:** 400 Bad Request  

**Expected Result:**
- Error lists missing mandatory fields.

---

## TC-API-11 – SQL Injection Attempt

**Expected Status:** 400 Bad Request  

**Expected Result:**
- Input sanitized.
- No SQL error thrown.

---

## TC-API-12 – XSS Attempt

**Expected Status:** 200 or 400  

**Expected Result:**
- Script escaped or rejected.
- No execution occurs.

---

## TC-API-13 – Retrieve Cart

**Endpoint:** `GET /cart`  
**Expected Status:** 200 OK  

**Expected Result:**
- JSON contains correct items and quantities.

---

## TC-API-14 – Unauthenticated User

**Expected Status:** 401 Unauthorized  

**Expected Result:**
- Error: "Please log in".

---

## TC-API-15 – Concurrent Requests

**Scenario:** 100 simultaneous requests  
**Expected Status:** 200 OK  

**Expected Result:**
- No race condition.
- Correct total quantity.
- Average response time < 2 seconds.

---

## TC-API-16 – Large Payload

**Expected Status:** 413 Payload Too Large or 400  

**Expected Result:**
- Server rejects oversized payload gracefully.
- No crash.
