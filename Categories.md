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
Then each product card contains image, name, price and actions  

---

## AC6 – Layout View Options
Given the user is on the category page  
When the user changes the view layout  
Then the product layout updates  

---

## AC7 – Cart and Watchlist Integration
Given the user clicks Add to Cart or Add to Watchlist  
Then the counter updates correctly  

---

## AC8 – Product Details Redirection
Given the user clicks product image  
Then user is redirected to product details page  

---

# 3️⃣ Test Cases

---------------------------------------------------------------------------------------

# Feature: Category Selection

## Functional – Valid Scenarios

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected results |
|------|------|------|------|------|------|
| **Category-FUNCV-01** | Validate selecting a category | High | User is browsing the store | 1. Click on a category | 1. User redirected to category page <br> 2. Correct products displayed |

---

## Functional – Invalid Scenarios

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected results |
|------|------|------|------|------|------|
| **Category-FUNCINV-01** | Validate selecting category without internet | Low | User is browsing store | 1. Disconnect internet <br> 2. Select category | No internet page appears |

---

## Edge Cases

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected results |
|------|------|------|------|------|------|
| **Category-EDGE-01** | Validate spam clicking category | Low | User on category page | 1. Spam click category | System does not crash |

---------------------------------------------------------------------------------------

# Feature: Sorting

## Functional – Valid Scenarios

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected results |
|------|------|------|------|------|------|
| **Sort-FUNCV-01** | Validate sorting products | Medium | User on category page | 1. Click sort dropdown <br> 2. Select option | Products sorted correctly |

---

## Integration

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected results |
|------|------|------|------|------|------|
| **Sort-INT-01** | Validate sorting after display selection | Low | User on category page | 1. Select display number <br> 2. Select sort option | Sorting works with display settings |

---------------------------------------------------------------------------------------

# Feature: Display Per Page

## Functional – Valid Scenarios

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected results |
|------|------|------|------|------|------|
| **Display-FUNCV-01** | Validate number of products displayed | Medium | User on category page | 1. Select display number | Correct number of products shown |

---------------------------------------------------------------------------------------

# Feature: Filters

## Functional – Valid Scenarios

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected results |
|------|------|------|------|------|------|
| **Filter-FUNCV-01** | Validate filtering by manufacturer | Medium | User on category page | 1. Select manufacturer | Correct products appear |
| **Filter-FUNCV-02** | Validate color filtering | Medium | User on Apparel category | 1. Select color | Matching products appear |
| **Filter-FUNCV-03** | Validate multiple filters | Medium | User on category page | 1. Apply two filters | Products match both filters |

---------------------------------------------------------------------------------------

# Feature: Product Card Actions

## Functional – Valid Scenarios

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected results |
|------|------|------|------|------|------|
| **Cart-FUNCV-01** | Validate Add to Cart | High | User on category page | 1. Click Add to Cart | Confirmation message appears |
| **Wishlist-FUNCV-02** | Validate Add to Wishlist | High | User on category page | 1. Click Add to Wishlist | Confirmation message appears |
| **CompareList-FUNCV-03** | Validate Add to Compare List | High | User on category page | 1. Click Compare | Product added to compare list |
| **Rent-FUNCV-04** | Validate Rent button | High | User on category page | 1. Click Rent | User redirected to product details |

---

## Edge Cases

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected results |
|------|------|------|------|------|------|
| **Cart-EDGE-01** | Validate spam clicking Add to Cart | High | User on category page | 1. Spam click Add to Cart | System stable |

---------------------------------------------------------------------------------------

# Feature: Counters Integration

## Integration

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected results |
|------|------|------|------|------|------|
| **Cart-INT-01** | Validate cart counter update | Low | User on category page | 1. Add product to cart | Counter increases |
| **Wishlist-INT-02** | Validate wishlist counter update | Low | User on category page | 1. Add product to wishlist | Counter increases |

---------------------------------------------------------------------------------------

# Feature: Product Navigation

## Functional – Valid Scenarios

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected results |
|------|------|------|------|------|------|
| **Product-FUNCV-01** | Validate product details redirection | High | User on category page | 1. Click product image | Redirect to product details page |

---------------------------------------------------------------------------------------

# Feature: Layout View

## UI Testing

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected results |
|------|------|------|------|------|------|
| **ProductCard-UI-01** | Validate product card layout | High | User on category page | 1. Observe card | Card contains correct elements |
| **Layout-UI-02** | Validate product alignment | High | User on category page | 1. Observe layout | Cards aligned correctly |
| **PageLayout-UI-03** | Validate page layout | High | User on category page | 1. Observe page | Page structure correct |

---------------------------------------------------------------------------------------

# Feature: Usability

## Usability Testing

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected results |
|------|------|------|------|------|------|
| **Accessibility-USB-01** | Validate alt text | High | User on category page | 1. Hover image | Alt text appears |
| **Accessibility-USB-02** | Validate screen reader support | High | Screen reader installed | 1. Open page | Reader reads elements |
| **Navigation-USB-03** | Validate keyboard navigation | Low | User on page | 1. Use Tab keys | Focus moves correctly |
| **Readability-USB-04** | Validate text readability | High | User on page | 1. Observe text | Font readable |

---------------------------------------------------------------------------------------

# Feature: API

## Valid Request

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected results |
|------|------|------|------|------|------|
| **Cart-APIV-01** | Validate Add to Cart API | High | Using Postman | 1. Send request | Status 200 |

---

## Invalid Request

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected results |
|------|------|------|------|------|------|
| **Cart-APIINV-01** | Validate Add to Cart API offline | High | Using Postman | 1. Disconnect internet <br> 2. Send request | Status 400 |
