# Feature: <Feature Name>

---

# 1️⃣ User Story
As a user,  
I want a category page,  
So I can specify the viewed products.

---

# 2️⃣ Acceptance Criteria (BDD)

## AC1 – 
Given the user is on the categories page
When the user chooses a category
Then only related products appear

## AC2 – 
Given the user is using the store
When the user is on the categories page
Then a main categories filter appears
And subcategories appear under their parents

## AC3 – 
Given is on the categories page
When the user selects a specific category
Then a sort of options will appear
And the user can sort products by (name/price)
And the user can select the number of products viewed per page (3,6,9)

## AC4 – 
Given is on the categories page
When the user selects a specific category
Then a maximum of 9 products are shown per page
And a minimum of 3 products per page

## AC5 – 
Given is on the categories page
When the user selects the Electronics category
Then the user chose three subcategories (Camera & Phone, Cell Phones, Others)
And the user will be able to filter according to the manufacturer
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
