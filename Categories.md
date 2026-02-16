# Feature: Category Page

---------------------------------------------------------------------------------------

# 1️⃣ User Story

As a user,  
I want to browse products by category,  
So that I can easily find relevant items.

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
| TC-FUNCV-01 | | | |

**Steps:**
1.  
2.  

**Expected Result:**
-  
-  

---

## Functional – Invalid Scenarios

| TC ID | Title | Priority | Preconditions |
|-------|-------|----------|---------------|
| TC-FUNCINV-01 | | | |

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

## API Testing (If applicable)

### Valid Request
- Status Code:
- Response Body:
- Database Check:

### Invalid Request
- Status Code:
- Error Message:
- Data Integrity:
