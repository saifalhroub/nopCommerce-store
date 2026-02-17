# Feature: Category Page

---------------------------------------------------------------------------------------

# 1️⃣ User Story

As a user,
I want to browse products by category with sorting and filtering options,
So that I can easily find products that match my preferences.

---------------------------------------------------------------------------------------

# 2️⃣ Acceptance Criteria (BDD)

## AC1 – Display Products by Category
Given the user is on the categories page  
When the user selects a category  
Then only products related to that category are displayed  

---

## AC2 – Sorting and Pagination
Given the user selected a category  
When the products are displayed  
Then the user can sort products by name or price  
And the user can select number of products per page (3, 6, 9)  
And the system enforces a minimum of 3 and maximum of 9 products per page  

---

## AC3 – Subcategories and Manufacturer Filter
Given the user selects a category that contains subcategories  
Then related subcategories are displayed  
And a manufacturer filter is available  

---

## AC4 – Price Range Filter
Given the user selected a category  
When the user sets a price range  
Then only products within the selected range are displayed  

---

## AC5 – Product Card Components
Given the products are displayed  
Then each product card contains:
- Product image  
- Product name  
- Price  
- Add to Cart button  
- Add to Watchlist button  
- Compare option  
- Rating indicator
- A rent option for specific products

---

## AC6 – Layout View Options
Given the user is on the category page  
When the user changes the view layout option  
Then the product display layout updates accordingly  

---

## AC7 – Cart and Watchlist Integration
Given the user clicks Add to Cart or Add to Watchlist  
Then the corresponding counter updates correctly  

---

## AC8 – Product Details Redirection
Given the user clicks on a product image  
Then the user is redirected to the product details page  

---
# 3️⃣ Test Cases

---

## Functional – Valid Scenarios

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-FUNCV-01 | Validate Selecting a category | High | user is using the store  |

**Steps:**
1.  Click on any category on the categories bar
2.  Observe the products that showed up

**Expected Result:**
-  User is redirected to the category products page
-  All products displayed are related to the chosen category

---

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-FUNCV-02 | Validate sort functionality | medium | user is on the products page |

**Steps:**
1.  Click on the sort by drop-down list
2.  Select the sorting criteria
3.  Observe the product's order

**Expected Result:**
-  Products are rearranged according to the selected sorting option 

---

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-FUNCV-03 | Validate the number of products displayed | medium | user is on the products page |

**Steps:**

1.  Click on the display per page drop-down list
2.  Select the number of products to be displayed
3.  Observe the product's number

**Expected Result:**
-  The number of products displayed matches the selected (Display per page)
-  The products appears are the ones at the top
-  The products on the bottom move to the next page

---



| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-FUNCV-04 | Validate the filteration using manufacturer | user is on the products page |

**Steps:**
1.  Select a manufacturer filter option
3.  Observe the displayed products

**Expected Result:**
- Only products that match the manufacturer will appear
---

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-FUNCV-05 | Validate the filteration using color filter for Apparel category | user is on the Apparel products page |

**Steps:**
1.  Select a subcategory
2.  Select the color
3.  Observe the displayed products

**Expected Result:**
- Only products that match the color will appear
---

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-FUNCV-06 | Validate selecting more than one filter | medium | user is on the products page |

**Steps:**
1.  Select a filter option
2.  Select another filter option
3.  Observe the displayed products

**Expected Result:**
-  The products that are displayed must match the two filterization criteria
-  No crash occurs in the system the system

---

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-FUNCV-07| Validate add to cart functionality | High | user is on the products page |

**Steps:**
1.  Click on add to cart button


**Expected Result:**
-  A confirmation message will appear telling user that: (the product has been added to your shopping cart)
  
---

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-FUNCV-08| Validate add to wishlist functionality | High | user is on the products page |

**Steps:**
1.  Click on add to wishlist button


**Expected Result:**
-  A confirmation message will appear telling user that: (the product has been added to your wishlist)
  
---

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-FUNCV-09| Validate add to compare list functionality | High | user is on the products page |

**Steps:**
1.  Click on add to compare list


**Expected Result:**
-  A confirmation message will appear telling user that: (the product has been added to your comparinglist)
  
---

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-FUNCV-10 | Validate the rent button functionality | High | user is on the products page |

**Steps:**
1.  Navigate to the jewellery category
2.  Click on the rent button for the (Elegant Gemstone Necklace) product

**Expected Result:**
-  The User is redirected to the product details page
-  The user will be asked to provide some details to confirm the process
  
---
## Functional – Invalid Scenarios

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-FUNCINV-01 | Validate selecting a product category while no internet connection established | low | User is using the store |

**Steps:**
1.  Cut-off the internet connection
2.  Select a category 

**Expected Result:**
-  User is redirected to no internet connection page
-  The request is sent to the server 
-  The request is accepted when the internet connection is back

---


## Integration

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-INT-01 | Validate sorting after determining the number of displayed products  | low | user is on the products page |

**Steps:**
1.  Click on the display per page drop-down list
2.  Select the number of products to be displayed
3.  Click on the sort by drop-down list
4.  Select the sorting criteria
5.  Observe the product's 

**Expected Result:**
-  The number of products displayed matches the selected (Display per page)
-  Products are rearranged according to the selected sorting option
-  No crashes occur in the system

---

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-INT-02| Validate the number of products appears on the  cart when adding a product to the cart | low | user is on the products page |

**Steps:**
1.  Click on add to cart button
2.  Observe the number beside the cart link at the top of the page

**Expected Result:**
-  The number changes accordingly after each add to the cart process
  
---

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-INT-03| Validate the number of products appears on the wishlist link when adding a product to the wishlist | low | user is on the products page |

**Steps:**
1.  Click on add to wishlist button
2.  Observe the number beside the wishlist link at the top of the page

**Expected Result:**
-  The number changes accordingly after each add to the wishlist process
  
---

## Edge Cases

| TC ID | Scenario | Expected Result |
|-------|----------|----------------|

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-EDGE-01| Validate spam clicking on category name | low | user is on the products page |

**Steps:**
1.  Spam click on the category name
2.  Observe the page response
**Expected Result:**
-  No crashes occur in the system
-  The spam clicked category products are the ones displayed
-  Each time a request is sent to the server and recorded
  
---

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-EDGE-02| Validate spam clicking on add to cart button | high | user is on the products page |

**Steps:**
1.  Spam click on the add to cart button
2.  Observe the system response
   
**Expected Result:**
-  No crashes occur in the system
-  Each click is handled like a separate request
-  With each click, a new item is added to the cart
  
--- 

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-EDGE-03| Validate spam clicking on add to wishlist button | low | user is on the products page |

**Steps:**
1.  Spam click on the add to the wishlist button
2.  Observe the system response
   
**Expected Result:**
-  No crashes occur in the system
-  Each click is handled like a separate request
-  With each click, a new item is added to the wishlist
  
--- 

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-EDGE-04| Validate spam clicking on add to comparing list button | low | user is on the products page |

**Steps:**
1.  Spam clicks on the add to Comparing List button
2.  Observe the system response
   
**Expected Result:**
-  No crashes occur in the system
-  only one request is accepted
-  Everyrequest is sent has the same outcome 
  
--- 

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-EDGE-05| Validate refreshing the page after adding products to cart/wishlist | high | user is on the products page |

**Steps:**
1.  Add product to the cart/wishlist
2.  Refresh the page
3.  Observe the number of products on the cart link/wishlist link
   
**Expected Result:**
-  Added products to cart/wishlist remains the same after adding and before refresh
  
--- 
## Security Testing

| TC ID | Attack Type | Expected Result |
|-------|------------|----------------|

-----NO NEED-----
---

## UI Testing

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-UI-01| Validate Product card layout | high | user is on the products page |

**Steps:**
1.  Observe the product card elements
   
**Expected Result:**
-  Product card has:
   - Image
   - Price
   - Add to cart button
   - Add to compare list button
   - Add to wishlist button
   - Rent buttons for some products
   - Review rating bar

--- 

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-UI-02| Validate the product has the right infromations | high | user is on the products page |

**Steps:**
1.  Observe the product name & image
   
**Expected Result:**
-  Product Image must match its name

---

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-UI-03| Validate the products layout and alignment | high | user is on the products page |

**Steps:**
1.  Observe the product's layout and alignment
   
**Expected Result:**
-  All products have the same card size (image, Text)
-  No overlapping between products card

---
| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-UI-03| Validate page layout and design | high | user is on the products page |

**Steps:**
1.  Observe the product page elements alignment
   
**Expected Result:**


## Usability Testing

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-USB-01| Validate Alternative text appears when hovering over page elements | high | user is on the products page |

**Steps:**
1.  Hover over product image
2.  Observe the alternate text that will appear
   
**Expected Result:**
-  Alternative text will appear describing the product image
  
--- 

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-USB-02| Validate page supports screen reader apps| high | User installed a screen reader appilcation |

**Steps:**
1.  Open screen reader application
2.  Navigate to the prducts page
   
**Expected Result:**
-  Screen reader should be able to read page elements
  
--- 

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-USB-03| Validate navigation using keyboard keys | low | user is on the products page |

**Steps:**
1.  Click on the tab button to move forward to the next element
2.  Click on tab + shift to move backward to the previous element 

   
**Expected Result:**
-  Focus response correctly
   - On the next field, when clicking on the tab button
   - on the previous field when clicking on the tab + shift button
  
---

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-USB-04| Validate Texts readability | high | user is on the products page |

**Steps:**
1.  Observe :
    - Font size is comfortable and easy to read with a size of (12px)
    - Font color is different from the page color
    - All texts have the same language

   
**Expected Result:**
-  Focus response correctly
   - On the next field, when clicking on the tab button
   - on the previous field when clicking on the tab + shift button
  
---
## Compatibility Scenarios

NO NEED Because it will consume a lot of time and effort, I will make a Global Test Suite for this Test type


## API Testing (If applicable)

### Valid Request

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-APIV-01| Validate Adding product to cart API response (code/Time/Body) | high | user is on Postman |

**Steps:**
1.  Submit an add to cart request
   
**Expected Result:**
-  Response status code is 200
-  Response Time is < 3s
-  Response body: (Product name, Product ID, Amount of added product, Product price)
  


### Invalid Request

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-APIINV-01| Validate Adding product to cart API response (code/Time/Body) while offline | high | user is on Postman |

**Steps:**
1.  Cut-off Internet connection 
2.  Submit an add to cart request
   
**Expected Result:**
-  Response status code is 400
-  Response Time is < 3s
-  Response body: Bad request
  
--- 

