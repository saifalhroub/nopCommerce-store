

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
