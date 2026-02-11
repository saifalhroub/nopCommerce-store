# Landing Page – Testing Coverage
Based on **Landing Page – User Stories & Acceptance Criteria (BDD)**

---

## Functional Testing

### ✅ Valid Scenarios

**US1.2**
- Validate moving through hero slides
- Validate redirection to product details page when clicking on **Learn More**

**US1.6**
- Validate navigating to category pages

**US1.7**
- Validate the **Add to Cart** button functionality

**US1.8**
- Validate searching for a product using its name
- Validate searching for a product using its category name

**US1.9**
- Verify redirection to the **Register** page when clicking on the register link

**US1.10**
- Verify redirection to the **Login** page when clicking on the login link

**US1.11**
- Verify logging out when clicking on the logout link

**US1.12**
- Verify redirection to **My Account** when clicking on the account link

**US1.13**
- Validate redirection to the **Cart** page when clicking on the cart icon

**US1.14**
- Validate redirection to the **Wishlist** page when clicking on the wishlist icon

**US1.15**
- Validate changing currency using the currency selector

---

### ❌ Invalid Scenarios

**US1.8**
- Validate searching for a product in another language
- Validate leaving the search bar empty

---

### ⚠️ Edge Cases

**US1.0**
- Verify navigating to the store landing page with no internet connection
- Verify opening the landing page simultaneously from two tabs

**US1.2**
- Validate clicking **Learn More** with no internet connection
- Validate excessive clicking on **Learn More**
- Validate opening product details page using **Open in New Tab**

**US1.6**
- Validate navigating to category pages with no internet connection

**US1.7**
- Validate adding a featured product to cart with no internet connection

**US1.8**
- Validate searching using product description
- Validate searching with no internet connection
- Validate copy & paste of product name into search bar
- Validate refreshing the page while the search bar is active
- Validate refreshing after filling the search bar before submitting

**US1.11**
- Validate logging out with no internet connection

**US1.12**
- Validate navigating to **My Account** with no internet connection

**US1.13**
- Validate navigating to the cart with no internet connection
- Validate adding products to cart with no internet connection

**US1.14**
- Validate navigating to the wishlist with no internet connection
- Validate adding products to wishlist with no internet connection

**US1.15**
- Validate changing currency while no internet connection is established

---

## Usability Testing

### ALL User Stories
- Validate navigation using keyboard only

**US1.0**
- Verify landing page layout and design (Priority: High)
- Verify landing page visuals as a guest
- Verify landing page visuals as a logged-in user
- Validate visual consistency between Dark / Light modes
- Validate visual consistency when rotating mobile screen

**US1.2**
- Validate hero image ratio across different screen sizes
- Validate slider navigation across different devices

**US1.3**
- Validate welcome message text correctness

**US1.6**
- Verify category page layout and design

**US1.7**
- Validate featured products show correct details

**US1.8**
- Validate search bar usability across devices
- Validate confirming search using **Enter**
- Validate confirming search using search icon
- Validate cursor appearance inside search bar
- Validate search bar border highlighting on focus

**US1.9**
- Validate register link visibility when logged out

**US1.10**
- Validate login link visibility when logged out

**US1.11**
- Validate logout link visibility when logged in
- Validate logout link changes to login after logout
- Validate **My Account** link changes to register after logout

**US1.12**
- Validate **My Account** link visibility when logged in

**US1.13**
- Validate cart item count updates correctly when adding products

**US1.14**
- Validate wishlist item count updates correctly when adding products

**US1.15**
- Validate product prices update based on selected currency

---

## Performance Testing

**US1.0**
- Validate landing page load time

**US1.2**
- Validate slider response time

**US1.6**
- Validate category navigation response time

**US1.8**
- Validate search response time

**US1.9**
- Validate register page navigation response time

**US1.10**
- Validate login page navigation response time

**US1.11**
- Validate logout response time

**US1.12**
- Validate **My Account** page navigation response time

**US1.13**
- Validate cart page navigation response time

**US1.14**
- Validate wishlist page navigation response time

---

## Security Testing

**US1.11**
- Validate session termination when navigating back using browser back button after logout

---

## API Testing

**US1.8**
- Validate product search API response from the store

---

## Compatibility Testing

### ALL User Stories
- Validate compatibility across different devices
- Validate opening the store using different internet connections
- Validate usage across different browsers and operating systems


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
