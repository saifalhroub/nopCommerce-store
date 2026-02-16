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
| TC-FUNCV-Integration-04 | Validate sorting after determining the number of displayed products  | low | user is on the products page |

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
| TC-FUNCV-05 | Validate the filter functionality | medium | user is on the products page |

**Steps:**
1.  Select a filter option
3.  Observe the product's displayed

**Expected Result:**
-  Only matched filter products appears

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

## Functional – Invalid Scenarios

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-FUNCINV-01 | Validate selecting a category while no internet connection is established | low | User is using the store |

**Steps:**
1.  Cut-off the internet connection
2.  Select a category 

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

## API Testing (If applicable)

### Valid Request
- Status Code:
- Response Body:
- Database Check:

### Invalid Request
- Status Code:
- Error Message:
- Data Integrity:
