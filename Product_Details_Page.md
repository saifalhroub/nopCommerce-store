

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
