# Feature: <Feature Name>

---

# 1️⃣ User Story
As a user,  
I want to view the product details page,  
So that I can get more information about the product.

---

# 2️⃣ Acceptance Criteria (BDD)

## AC1 – 
Given the user is on product page
When the user clicks on product image
Then the user will be redirected to product details page

## AC2 – 
Given the user is using the store
When the user is on the product details page
Then the product details will appear:
 - Product name
 - Product description
 - Product price
 - Review rating

## AC3 – 
Given the user is on the product details page
When the user decides to add a product to the cart
Then the user will click on the add to cart button
And the user will be able to determine the number of the same product to be added

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
-  A confirmation message will show up
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

| TC-FUNCV-08 | Validate leaving a review while logged in | low | User is on product details page |

**Steps:**
1. Fill all mandatory fields with valid data
2. Click on the Submit Review button
   
**Expected Result:**
-  A confirmation message will show up: "Product review is successfully added."
-  The Review will appear in the Existing reviews section and contains:
   - Review Title
   - Rating bar
   - Review text
   - Reviewer name
   - Date and time of publishing 
---

| TC-FUNCV-08 | Validate adding to the cart a shoe with its color and size  | hig | User is on the shoe details page |

**Steps:**
1. Select the shoe color
2. Select the shoe size
3. Click on add to cart button
   
**Expected Result:**
-  A confirmation message will show up
-  The total number appear beside the add to cart link will change accordingly
-  The product will be added to the Cart
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

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-FUNCINV-02 | Validate Adding a negative number for the product quantity | High | User is on product details page |

**Steps:**
1. Fill the quantity field with a negative number
2. Click on the add to the cart button
   
**Expected Result:**
- No product is added to the Cart
- A clear error message telling the user: "Quantity should be positive."

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

**Steps:**
1. Leave all mandatory fields empty
2. Click on the add to cart button
   
**Expected Result:**
- An error message will appear telling the user: "Please select (......)."
- No product is added to the cart

---

| TC-FUNCINV-07 | Validate leaving all mandatory shoes fields empty | High | User is on product details page |

**Steps:**
1. Leave all mandatory fields empty
2. Click on the add to cart button
   
**Expected Result:**
- An error message will appear telling the user: "Please select (......)."
- No product is added to the cart

---

| TC-FUNCINV-08 | Validate leaving shoes color field empty | High | User is on product details page |

**Steps:**
1. Select shoes color
2. Leave shoes size empty
3. Click on the add to cart button
   
**Expected Result:**
- An error message will appear telling the user: "Please select the shoe size."
- No product is added to the cart

---

| TC-FUNCINV-09 | Validate leaving shoes size field empty | High | User is on product details page |

**Steps:**
1. Select shoes size
2. Leave shoes color empty
3. Click on the add to cart button
   
**Expected Result:**
- An error message will appear telling the user: "Please select the shoe color."
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

| TC-BVA-03 | Validate adding a zero copies of a product les than the min allowed 1| High | User is on product details page |

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

| TC ID | Scenario | Expected Result |
|-------|----------|----------------|

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-EDGE-01 | Validate write the number in letters | low | User is on product details page |

**Steps:**
1. Fill the quantity field with a number in letters
2. Click on the add to the cart button
   
**Expected Result:**
- No product is added to the Cart
- A clear error message telling the user: "Quantity should be positive"

---

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-EDGE-02 | Validate writting a special character in the quantity field | low | User is on product details page |

**Steps:**
1. Fill the quantity field with a number in letters
2. Click on the add to the cart button
   
**Expected Result:**
- No product is added to the Cart
- A clear error message telling the user: "Quantity should be positive"

---
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

