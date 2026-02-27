# Order Information page

> As a user,
> I want an order information page
> So I can check and manage my order 

---

## AC - Order information preview

Given the user has submitted an order 
When the user is on the order information page
Then the user will see:
  - Print button
  - PDF Invoice button
  - Cancel order button
  - Order Number
  - Order Date
  - Order Status
  - Order total, subtotal, tax, shipping & gift wrapping price
  - Billing Address
  - Shipping Address
  - Payment informations
  - Shipping method and price
  - Products
  - Reorder button

---
    
## AC - Order Cancelation

Given the user has submitted an order
When the user is on the order information page
Then the system will allow the user to cancel his order

---

## AC - Print informatiom

Given the user wants to have a hard copy of the order informations 
When the user is on the order information page
Then the store allow user to print the order informations

## AC - Print information flow

Given that the user is on the order information page
When the user clicks on the print button
Then the user will be redirected to a new tab
And the tab contains print settings

---

## AC - PDF Invoice
Given the user is on the order information page
When the user clicks on the PDF Invoice button
Then the order information will be downloaded as PDF

---

## AC - Reorder 
Given that the user is on the order information page
When the user clicks on the reorder button
Then the user will be redirected to the cart page
And the same products that have been in the order will appear

---

# Core functionalities

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| --- | --- | --- | --- | --- | --- |
| **FUNC-Canncel-01** | Validate cancelling the order | High | Order Accepted, and the user is on the order information page | 1. Click on the cancel button <br> 2. Confirm the deletion process | 1. Order is cancelled <br> 2. System will send a message confirming the order cancellation <br> 3. The cancel button disappears <br> |
| **FUNC-Print-02** | Verify user can print the order information | Low | Order information page loaded | 1. Click on the print button <br> 2. Determine the print settings <br> 3. Confirm the print | 1. User is redirected to a print setting page <br> 2. The order information is printed |
| **FUNC-PDF-03** | Low | Verify user can have a soft copy of the order information | Order information page loaded | 1. Click on the PDF Invoice | 1. A download will start <br> 2. The pdf will be stored in the user's device |
| **Func-Reorder-04** | High | Validate reordering the same order | Order information page loaded | 1. Click on the reorder button | 1. The system redirects the user to the cart page <br> 2. The same products in the placed order appear with the right quantity <br> 3. The user is allowed to change the quantity of the product

---

# Edge & Robutness
| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| --- | --- | --- | --- | --- | --- |
| **EDGE-internet-01** | Validate the page response to no internet connection | Medium | Order information page loaded | 1. Turn off th wifi <br> 2. Send request a request for any functionality | 1. The system will redirect the user to no internet connection page <br> 2. The request will be processed after user connects the device to the internet |
| **EDGE-refresh-02** | Validate refreshing the page after cancelling order | Medium | Order information page loaded | 1. Cancel order <br> 2. Refresh the page | 1. The order state remains cancelled <br> 2. No new order placed |
| **EDGE-refresh-03** | Validate using the page with 3G throttling | High | Order information page loaded| 1. use the page and make orders | 1. The system responds correctly <br> 2. No crash |
| **ROBU-cancel-04** | Validate spame clicking on the cancel button | Medium | Order information page loaded | 1. Click for a consecutive times on the cancel button | 1. The page is disabled <br> 2. A confirm canceling message appears <br> 3. The system prevent the user from interacting with the page | 
| **ROBU-Print&PDF-05** | Validate spame clicking on the print button | Medium | Order information page loaded | 1. Click for a consecutive times on the print button | 1. The system responds to the first click only <br> 2. The user is redirected to only one new tab for print request <br> 3. Only one download will start for PDF Invoice  | 

---

# UI - Global

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| --- | --- | --- | --- | --- | --- |
| **UI-layout-01** | Verify page elements consistency & alignment | High | Order information page loaded | Observe the page layout | 1. All elements are consistent with (size, shape) <br> 2. Page elements will aligned no overlapping is noticed |

---

# Compatibility - Global

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| --- | --- | --- | --- | --- | --- |
| **COMP-Browsers-01** | Validate page functionality with major browsers | High | User has access to different browsers | 1. Navigate to the page with each browser <br> 2. Use the page | 1. System respond correctly to different browsers |
| **COMP-Devices-02** | Validate page responsivness with different devices | High | User has access to different diveces | 1. Navigate to the page with each device | 1. Page adapts to every decvice screen dimensions correctly <br> 2. No overlapping between page elements <br> 3. No crash |
| **COMP-OS-03** | Validate page functionality with operating systems | High | User has access to different OS | 1. Navigate to the page with each OS <br> 2. Use the page | 1. System respond correctly to different OS |

---

# Performence - Global

> The response time is according to amazon recommended response time

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| --- | --- | --- | --- | --- | --- |
| **PFM-buttons-01** | Validate page's button response time | High | Order information page loaded | 1. Make an action with each burron <br> 2. observe the system response time | 1. Response tiime is </equal 3 seconds |
| **PFM-internet-02** | Validate page response time to different internet connections | Medium | User has access to different internet connections | 1. Navigate to the order information page with each connection <br> 2. Make action | 1. Response tiime is </equal 3 seconds for all connections |    
---

# Usability - Global

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
| --- | --- | --- | --- | --- | --- |
| **USB-keyboard-01** | Validate navigation using keyboard keys | low | Oredr information page loaded | 1. Click on the tab button to move forward to the next button <br> 2. Click on the tab + shit buttons to move backward to the previous button |
| **USB-Cursor-02** | Verify cursor state change when hovering over different elements | low | Order information page loaded | 1. Hover over any button | 1. Cursor will change from arrow to pointer when hover over button/link <br> 2. Cursor will change from arrow to text cursor when hovering over headings/paragraphs <br> 3. Cursor will change from arrow to not-allowed cursor when dragging button element | 

---------------------------------------------------------------------------------------------------------
!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!

# Feature: Order Information Page

> As a user,
> I want to view my order information
> So that I can track, manage, or reuse my order

---

# Business Rules

- Cancel button is visible ONLY when:
  - Order status = Pending or Processing
  - Order not shipped
  - Order not already cancelled

- Reorder is available only if:
  - Products still exist in catalog

---

# Acceptance Criteria

## AC – Order Information Preview

Given the user has successfully placed an order  
When the user navigates to Order Information page  
Then the system displays:

- Order Number
- Order Date
- Order Status
- Billing Address
- Shipping Address
- Shipping Method and cost
- Payment Method
- Products (name, quantity, price)
- Subtotal, Shipping, Tax, Total
- Print button
- PDF Invoice button
- Cancel button (if applicable)
- Reorder button

---

## AC – Cancel Order

Given the order status allows cancellation  
When the user clicks Cancel  
And confirms the action  
Then:

- Order status changes to Cancelled
- Cancel button disappears
- Confirmation message is shown
- Order remains cancelled after page refresh

---

## AC – Print Order

Given the user is on Order Information page  
When the user clicks Print  
Then:

- A new tab opens
- Printable version of the order is displayed
- Browser print dialog appears

---

## AC – PDF Invoice

Given the user is on Order Information page  
When the user clicks PDF Invoice  
Then:

- A PDF file is downloaded
- The file contains accurate order information

---

## AC – Reorder

Given products are still available  
When the user clicks Reorder  
Then:

- User is redirected to Cart page
- Same products are added with correct quantities
- User can modify quantities before checkout

---

# Core Functional Test Cases

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
|---|---|---|---|---|---|
| TC-ORD-01 | View order details | High | Valid order exists | Open order page | All order data displayed correctly |
| TC-ORD-02 | Cancel eligible order | High | Order status = Pending | Click Cancel → Confirm | Status becomes Cancelled, button disappears |
| TC-ORD-03 | Prevent cancelling shipped order | High | Order status = Shipped | Attempt cancel | Cancel option not available |
| TC-ORD-04 | Reorder available products | High | Products active | Click Reorder | Items added to cart correctly |
| TC-ORD-05 | Reorder with removed product | Medium | Product removed from catalog | Click Reorder | System shows product unavailable message |
| TC-ORD-06 | Download PDF invoice | Medium | Order exists | Click PDF | PDF downloaded successfully |
| TC-ORD-07 | Print order | Low | Order page loaded | Click Print | Printable page opens in new tab |

---

# Edge & Robustness

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
|---|---|---|---|---|---|
| TC-EDGE-01 | Refresh after cancellation | Medium | Order cancelled | Refresh page | Status remains Cancelled |
| TC-EDGE-02 | Spam clicking Cancel | Medium | Order eligible | Click multiple times rapidly | Only one cancellation processed |
| TC-EDGE-03 | Change order ID in URL | High | Logged in user | Modify order ID manually | Access denied or error shown |
| TC-EDGE-04 | No internet during action | Medium | Page loaded | Disable internet → Click action | Proper error message displayed |

---

# Security Considerations (Observed Level Only)

| TC ID | Title | Priority | Expected Result |
|---|---|---|---|
| TC-SEC-01 | Unauthorized order access | High | User cannot view other users' orders |
| TC-SEC-02 | Direct invoice link access | High | Invoice cannot be accessed without authentication |

---

# UI – Global Test Cases

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
|---|---|---|---|---|---|
| TC-UI-01 | Verify layout consistency | High | Order page loaded | Observe layout elements | All elements aligned properly, no overlap |
| TC-UI-02 | Verify responsive behavior | High | Order page loaded | Resize browser window | Layout adapts correctly without breaking |
| TC-UI-03 | Verify mobile responsiveness | High | Access via mobile device | Open order page | Page adapts to screen size, no horizontal scroll |
| TC-UI-04 | Verify cross-browser compatibility | High | Access via Chrome, Firefox, Edge | Navigate and use page | Same functionality across browsers |

---

# Performance – UI Level Test Cases

| TC ID | Title | Priority | Preconditions | Steps | Expected Results |
|---|---|---|---|---|---|
| TC-PERF-01 | Validate initial page load time | High | Order exists | Open order page | Page loads within ≤ 3 seconds |
| TC-PERF-02 | Validate cancel action response time | High | Order eligible for cancellation | Click Cancel → Confirm | Status updates within ≤ 3 seconds |
| TC-PERF-03 | Validate PDF generation time | Medium | Order exists | Click PDF Invoice | File download starts within ≤ 5 seconds |
| TC-PERF-04 | Validate behavior under slow network | Medium | Throttle to 3G | Use page actions | Page remains functional without crash |

---

# Test Limitations

Due to training platform constraints:

- Backend API responses cannot be directly validated.
- Refund logic cannot be verified.
- Inventory restoration cannot be confirmed.
- Database-level consistency cannot be checked.

These areas are identified as potential risk points requiring backend testing.
