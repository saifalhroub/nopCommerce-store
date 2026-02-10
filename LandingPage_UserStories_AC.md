# Landing Page – User Stories & Acceptance Criteria (BDD)

## Scope
This document covers **Landing Page functionality only**.
It focuses on **visibility, navigation, and access to features**, without including
execution logic related to other pages (e.g. login validation, checkout flow).

---

## US1.0 View Landing Page

### User Story
As a visitor, I want to view the landing page so that I can understand what the store offers and decide whether to continue browsing.

### Acceptance Criteria (BDD)
- Given the visitor navigates to the website URL
- When the page finishes loading
- Then the landing page is displayed successfully
- And all main sections are visible
- And no broken layout or empty content is shown

---

## US1.1 Hero Section / Promotional Slider

### User Story
As a visitor, I want to see a hero section with promotional content so that I can quickly understand current offers.

### Acceptance Criteria (BDD)
- Given the visitor is on the landing page
- Then the hero section is displayed at the top of the page
- And promotional banners are visible
- And images are clear and readable

---

## 1.2 Slider Navigation Controls

### User Story
As a visitor, I want to control the promotional slider so that I can view offers at my own pace.

### Acceptance Criteria (BDD)
- Given the visitor is viewing the hero slider
- When the visitor clicks next or previous controls
- Then the slider navigates to the corresponding slide
- And the displayed content updates correctly

---

## 1.3 Welcome Message

### User Story
As a visitor, I want to see a welcome message so that I can understand the store’s purpose and value.

### Acceptance Criteria (BDD)
- Given the visitor is on the landing page
- Then a welcome message is visible
- And the message clearly explains the store purpose
- And the text does not overlap other elements

---

## 1.4 Call To Action (CTA)

### User Story
As a visitor, I want to see a clear call-to-action button so that I can start exploring the store.

### Acceptance Criteria (BDD)
- Given the visitor is on the landing page
- Then a CTA button is visible
- When the visitor clicks the CTA button
- Then the user is navigated to the intended page

---

## 1.5 Header Navigation Menu

### User Story
As a visitor, I want to use the header navigation menu to navigate between pages easily.

### Acceptance Criteria (BDD)
- Given the visitor is on the landing page
- Then the header navigation menu is visible
- When the visitor clicks on any menu item
- Then the corresponding page is opened

---

## 1.6 Product Categories Section

### User Story
As a visitor, I want to see product categories so that I can browse items by category.

### Acceptance Criteria (BDD)
- Given the visitor scrolls the landing page
- Then the categories section is visible
- And each category has a clear label
- When the visitor selects a category
- Then the category page is opened

---

## 1.7 Featured Products Section

### User Story
As a visitor, I want to see featured products so that I can discover highlighted items.

### Acceptance Criteria (BDD)
- Given the visitor is on the landing page
- Then the featured products section is visible
- And each product displays an image and name
- When the visitor clicks a product
- Then the product details page is opened

---

## 1.8 Search Access

### User Story
As a visitor, I want to access a search option so that I can quickly find products.

### Acceptance Criteria (BDD)
- Given the visitor is on the landing page
- Then the search option is visible
- When the visitor clicks the search input
- Then the search page or results view is opened

---

## 1.9 Register Link Visibility

### User Story
As a new visitor, I want to see a register link so that I can create an account.

### Acceptance Criteria (BDD)
- Given the visitor is on the landing page
- Then the register link is visible
- When the visitor clicks the register link
- Then the registration page is opened

---

## 1.10 Login Link Visibility

### User Story
As a visitor, I want to see a login link so that I can access the store using my credentials.

### Acceptance Criteria (BDD)
- Given the visitor is on the landing page
- Then the login link is visible
- When the visitor clicks the login link
- Then the login page is opened

---

## 1.11 Logout Link (Logged-in State)

### User Story
As a logged-in user, I want to see a logout link so that I can end my session.

### Acceptance Criteria (BDD)
- Given the user is logged in
- And the user is on the landing page
- Then the logout link is visible
- When the user clicks the logout link
- Then the user session ends
- And the landing page is displayed

---

## 1.12 My Account Link (Logged-in State)

### User Story
As a logged-in user, I want to see a My Account link so that I can manage my account information.

### Acceptance Criteria (BDD)
- Given the user is logged in
- And the user is on the landing page
- Then the My Account link is visible
- When the user clicks the My Account link
- Then the account page is opened

---

## 1.13 Cart Icon Visibility

### User Story
As a visitor, I want to see a cart icon so that I can access my selected items.

### Acceptance Criteria (BDD)
- Given the visitor is on the landing page
- Then the cart icon is visible
- When the visitor clicks the cart icon
- Then the cart page is opened

---

## 1.14 Wishlist Icon Visibility

### User Story
As a visitor, I want to see a wishlist icon so that I can access saved items.

### Acceptance Criteria (BDD)
- Given the visitor is on the landing page
- Then the wishlist icon is visible
- When the visitor clicks the wishlist icon
- Then the wishlist page is opened

---

## 1.15 Currency Selector

### User Story
As a visitor, I want to see a currency selector so that I can view prices in my preferred currency.

### Acceptance Criteria (BDD)
- Given the visitor is on the landing page
- Then the currency selector is visible
- When the visitor selects a currency
- Then prices are displayed in the selected currency

---

## 1.16 Footer Section

### User Story
As a visitor, I want to view the footer so that I can access additional information.

### Acceptance Criteria (BDD)
- Given the visitor scrolls to the bottom of the landing page
- Then the footer is displayed
- And footer links are visible and readable

---

## 1.17 Responsive Design

### User Story
As a visitor, I want the landing page to be responsive so that I can browse the store on any device.

### Acceptance Criteria (BDD)
- Given the visitor opens the landing page on different screen sizes
- Then the layout adapts correctly
- And no content overlaps or breaks

---

## 1.18 Accessibility

### User Story
As a visitor with accessibility needs, I want the landing page to be accessible so that I can use it without difficulty.

### Acceptance Criteria (BDD)
- Given the visitor navigates using keyboard or assistive tools
- Then all main content and interactive elements are accessible

---
