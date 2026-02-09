# Feature: Landing Page Functionality and Layout
  - As a user, I want to view and interact with the landing page, So that I can navigate the store and discover products

  ## Background:
    - Given I navigate to the store URL
    - and the homepage loads successfully 

  ### Scenario: Verify header navigation elements are visible
    When I view the page header
    Then I should see a currency selector dropdown
    And I should see a search bar with search button
    And I should see "Register" and "Log in" links
    And I should see "Wishlist" and "Shopping Cart" links

  ### Scenario: Verify promotional slider functionality
    When I view the main promotional slider
    Then I should see promotional images rotating
    And each promotion should have a "Learn More" button
    When I click "Learn More" for iPhone promotion
    Then I should be redirected to iPhone product page

  #### Scenario: Verify product categorization sections
    When I scroll to the main content area
    Then I should see top menu with categories
    And I should see category grid with thumbnails
    And I should see featured products section
    And each product should display price, rating, and "Add to cart" button

  ### Scenario: Verify footer information is complete
    When I scroll to the bottom of the page
    Then I should see footer divided into sections
    And I should see "Information & Customer Service" links
    And I should see "My Account" links
    And I should see social media icons
    And I should see newsletter subscription field
---------------

As a user, I want a login link, so I can use the store with my credentials

As a user, I want a register link, so I can use the store with my credentials 

As a user, I want a search bar, so I can look for specific products

As a user, I want a watchlist link, so I can addmy fav products to it

As a user, I want a shopping cart link, so I can take a look at my selected products

As a user, I want a landing page, so I can know the store logic

As a user, I want a currency selector, so I can change the product's value view currency



    
