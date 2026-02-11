# ✅ Landing Page – Test Cases (Manual QA)

---

## 🔹 Functional Testing (Landing Page Scope)

### US1.0 – View Landing Page
- Verify navigating to the landing page using the website URL
- Verify landing page loads successfully
- Verify all main sections are visible
- Verify no broken layout or missing content

---

### US1.1 – Hero Section Visibility
- Validate hero section is displayed at the top of the page
- Validate promotional images are visible and clear

---

### US1.2 – Hero Slider Controls
- Validate slider auto-rotation
- Validate navigating between slides using controls
- Validate slider indicators reflect the current slide

---

### US1.3 – Welcome Message
- Validate welcome message is visible
- Validate text clearly explains the store purpose
- Validate text does not overlap other UI elements

---

### US1.4 – Call To Action (CTA)
- Validate CTA button is visible
- Validate CTA button is clickable
- Validate CTA button has clear text

---

### US1.5 – Header Navigation Menu
- Validate header menu is visible
- Validate menu items are readable
- Validate menu is accessible on different screen sizes

---

### US1.6 – Categories Section
- Validate categories section visibility
- Validate each category has a clear label
- Validate category cards are clickable

---

### US1.7 – Featured Products Section
- Validate featured products section visibility
- Validate each product displays image and name
- Validate products are clickable

---

### US1.8 – Search Bar Visibility
- Validate search bar is visible
- Validate search input is clickable
- Validate placeholder text is displayed

---

### US1.9 – Register Link Visibility
- Validate register link is visible for guest users
- Validate register link text is clear

---

### US1.10 – Login Link Visibility
- Validate login link is visible for guest users
- Validate login link text is clear

---

### US1.11 – Logout Link Visibility
- Validate logout link is visible for logged-in users
- Validate logout link is hidden for guest users

---

### US1.12 – My Account Link Visibility
- Validate My Account link is visible for logged-in users
- Validate My Account link is hidden for guest users

---

### US1.13 – Cart Icon Visibility
- Validate cart icon is visible
- Validate cart icon is clickable

---

### US1.14 – Wishlist Icon Visibility
- Validate wishlist icon is visible
- Validate wishlist icon is clickable

---

### US1.15 – Currency Selector (Landing Page Scope)
- Validate currency selector is visible
- Validate currency dropdown opens
- Validate user can select a currency option
- Validate selected currency label updates in header

---

### US1.16 – Footer Section
- Validate footer is visible at the bottom of the page
- Validate footer links are readable
- Validate footer does not overlap page content

---

## ⚠️ Edge Cases (Landing Page Only)

### US1.0
- Verify landing page behavior with no internet connection
- Verify opening landing page in multiple browser tabs

---

### US1.2 – Slider
- Validate rapid clicking on slider controls
- Validate opening slider links in a new tab

---

### US1.8 – Search Bar
- Validate clicking search bar and refreshing page
- Validate copy & paste inside search bar

---

## ♿ Usability & Accessibility

### All User Stories
- Validate navigation using keyboard only
- Validate tab order is logical
- Validate focus indicator is visible

---

### Accessibility
- Validate images include alt text
- Validate sufficient contrast ratio
- Validate screen reader can read main sections

---

## 📱 Responsive Design

- Validate landing page layout on desktop
- Validate landing page layout on tablet
- Validate landing page layout on mobile
- Validate layout consistency on orientation change


# ✅ Landing Page – Comprehensive QA Test Cases

## 🔹 1. Functional Testing (User Actions & Logic)
*Focus: Does the system behave correctly when interacted with?*

### US1.0 – Page Initialization & Navigation
- **Initial Load:** Verify the landing page returns a 200 OK status code and loads within acceptable time limits.
- **URL Direct Access:** Verify that entering the direct URL takes the user to the correct landing page.
- **Refresh Behavior:** Verify that refreshing the page maintains the current session and selected language/currency.

### US1.1 – Hero Slider & CTA
- **Manual Navigation:** Verify clicking 'Next/Previous' arrows updates the slide and content.
- **Pagination Indicators:** Verify clicking slider dots/indicators navigates to the specific slide.
- **CTA Redirection:** Verify clicking the Primary CTA button (e.g., "Shop Now") redirects to the correct destination (Category or Promotion page).
- **Link Integrity:** Verify all links within the slider are functional and not leading to 404 pages.

### US1.2 – Header & Navigation Menu
- **Menu Links:** Verify each menu item (Home, Categories, About) redirects to its respective page.
- **Sticky Header:** Verify the header remains functional/accessible while scrolling (if applicable).
- **Cart Redirection:** Verify clicking the Cart icon opens the Cart drawer or redirects to the `/cart` page.

### US1.3 – Authentication Logic (Dynamic UI)
- **Guest State:** Verify that 'Login' and 'Register' links are functional for unauthenticated users.
- **Logged-in State:** Verify that 'My Account' and 'Logout' links appear only after a successful login.
- **Logout Action:** Verify that clicking 'Logout' terminates the session and redirects the user to the landing page or login screen.

### US1.4 – Search Functionality (Functional Scope)
- **Basic Search:** Verify that entering a valid product name and pressing 'Enter' or clicking the 'Search' icon returns relevant results.
- **Empty Search:** Verify that clicking search with an empty input does not trigger an unnecessary API call or shows a validation message.
- **Redirection:** Verify the search bar redirects to the Search Results Page (PLP).

### US1.5 – Categories & Featured Products
- **Category Navigation:** Verify clicking a Category card/image redirects to the filtered product list.
- **Product Interaction:** Verify clicking a product image or name redirects to the specific Product Details Page (PDP).
- **Wishlist Toggle:** Verify clicking the Wishlist icon on a product card adds/removes the item and updates the global wishlist counter.

### US1.6 – Currency Selector Logic
- **Currency Switch:** Verify that selecting a different currency (e.g., USD to EUR) updates all product prices across the landing page immediately.
- **Persistence:** Verify the selected currency is saved even after navigating away and returning to the landing page.

---

## 🎨 2. UI & Usability Testing (Visibility & Layout)
*Focus: Does the page look correct and follow design standards?*

- **Visual Consistency:** Validate that fonts, colors, and button styles match the style guide/Figma design.
- **Hero Visibility:** Validate that hero images are not pixelated and text overlays are readable.
- **Broken Images:** Validate that all product images and icons are loaded correctly (No broken image placeholders).
- **Footer Content:** Validate that social media icons, copyright text, and contact info are visible and correctly aligned.
- **Layout Integrity:** Validate that no elements (text/images) overlap on standard screen resolutions.

---

## ⚠️ 3. Edge Cases & Error Handling

- **Slow Network (Throttling):** Verify the page displays loading skeletons or spinners during high latency.
- **No Internet:** Verify the application displays a graceful "Offline" message or cached version (if PWA).
- **Rapid Clicks:** Verify that clicking the "Slider Next" or "Add to Cart" buttons rapidly doesn't cause UI glitches or multiple duplicate API requests.
- **Special Characters in Search:** Verify the search bar handles symbols (e.g., `@#$%^&*`) without breaking the layout or causing SQL errors.
- **Session Timeout:** Verify the UI updates (e.g., hiding 'My Account') if the user's session expires while they are on the landing page.

---

## 📱 4. Responsive & Accessibility

- **Breakpoints:** Validate layout transitions smoothly between Desktop (1440px), Tablet (768px), and Mobile (375px).
- **Hamburger Menu:** Verify the navigation menu transforms into a functional hamburger menu on mobile devices.
- **Keyboard Navigation:** Verify users can navigate through all links and buttons using only the `Tab` and `Enter` keys.
- **Alt-Text:** Verify all functional images (Logo, Products, Icons) have descriptive `alt` tags for screen readers.
- **Orientation:** Validate that the layout adjusts correctly when switching between Landscape and Portrait modes on mobile.
