# Landing Page – BDD User Stories & Test Cases

Test Target: Landing Page of nopCommerce store

---

# Feature: Landing Page Load

## User Story

As a visitor  
I want to open the landing page  
So that I can start exploring the store.

---

## Acceptance Criteria

Scenario: Landing page loads successfully  
Given the user has internet access  
When the user navigates to the website URL  
Then the landing page should load without errors

---

## Functional Tests

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| LP-FUNC-01 | Validate landing page loads | High | User has internet | 1. Navigate to website URL | Landing page loads successfully |

---

## UI Tests

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| LP-UI-01 | Validate landing page layout | Medium | Landing page opened | 1. Observe page layout | Page elements appear correctly without layout issues |

---

## Performance Tests

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| LP-PERF-01 | Validate landing page load time | High | Stable internet | 1. Navigate to landing page | Page loads within acceptable time (e.g. <3 seconds) |

---

# Feature: Hero Banner

## User Story

As a visitor  
I want to see the hero banner  
So that I can understand store promotions.

---

## Acceptance Criteria

Scenario: Hero banner visibility  
Given the landing page is opened  
When the user views the top section  
Then the hero banner should be displayed

---

## Functional Tests

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| HB-FUNC-01 | Validate hero banner visibility | High | Landing page opened | 1. Observe top section | Hero banner visible |

---

## UI Tests

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| HB-UI-01 | Validate banner image display | Medium | Landing page opened | 1. Observe banner image | Banner image displayed correctly |

---

## Usability Tests

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| HB-USAB-01 | Validate banner readability | Low | Landing page opened | 1. Observe banner text | Banner content clearly readable |

---

# Feature: Categories Section

## User Story

As a visitor  
I want to browse product categories  
So that I can navigate to relevant products.

---

## Acceptance Criteria

Scenario: Categories visibility  
Given the landing page is loaded  
When the user scrolls to the categories section  
Then category items should be visible

Scenario: Category navigation  
Given the categories section is visible  
When the user clicks a category  
Then the system should redirect to the category page

---

## Functional Tests

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| CAT-FUNC-01 | Validate categories visibility | High | Landing page opened | 1. Scroll to categories | Categories displayed |
| CAT-FUNC-02 | Validate category navigation | High | Categories visible | 1. Click category | Category page opens |

---

## UI Tests

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| CAT-UI-01 | Validate categories layout | Medium | Categories visible | 1. Observe categories alignment | Categories displayed correctly |

---

## Usability Tests

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| CAT-USAB-01 | Validate categories easy to identify | Medium | Landing page opened | 1. Observe categories | Categories clearly labeled |

---

# Feature: Featured Products

## User Story

As a visitor  
I want to see featured products  
So that I can discover highlighted items.

---

## Acceptance Criteria

Scenario: Featured products visibility  
Given the landing page is loaded  
When the user views the featured products section  
Then product cards should be displayed

Scenario: Product navigation  
Given featured products are visible  
When the user clicks a product  
Then the product details page should open

---

## Functional Tests

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| FP-FUNC-01 | Validate featured products section | High | Landing page opened | 1. Scroll to featured products | Product cards visible |
| FP-FUNC-02 | Open product details page | High | Product visible | 1. Click product card | Product page opens |

---

## UI Tests

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| FP-UI-01 | Validate product card alignment | Medium | Product cards visible | 1. Observe card layout | Cards aligned correctly |

---

## Performance Tests

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| FP-PERF-01 | Validate products loading speed | Medium | Landing page opened | 1. Scroll to products | Products load without delay |

---

## Edge Tests

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| FP-EDGE-01 | No featured products available | Low | Featured products disabled | 1. Open landing page | System shows empty state |

---

# Feature: Promotions / CTA

## User Story

As a visitor  
I want to see promotional banners or CTA buttons  
So that I can access offers quickly.

---

## Acceptance Criteria

Scenario: Promotion visibility  
Given the landing page is loaded  
When the user views promotional banners  
Then promotional content should appear

Scenario: Promotion navigation  
Given a CTA button is visible  
When the user clicks the button  
Then the system should redirect to the target page

---

## Functional Tests

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| PROMO-FUNC-01 | Validate promotional banner visibility | Medium | Landing page opened | 1. Observe promotion section | Promotion displayed |
| PROMO-FUNC-02 | Validate promotion navigation | Medium | Promotion visible | 1. Click CTA | Correct page opens |

---

## Usability Tests

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| PROMO-USAB-01 | Validate CTA clarity | Low | Landing page opened | 1. Observe CTA | CTA easy to understand |

---

# Feature: News Section

## User Story

As a visitor  
I want to view store news  
So that I can stay updated.

---

## Acceptance Criteria

Scenario: News section visibility  
Given the user is on the landing page  
When the user scrolls the page  
Then the news section should appear

---

## Functional Tests

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| NEWS-FUNC-01 | Validate news section visibility | Medium | Landing page opened | 1. Scroll page | News section visible |
| NEWS-FUNC-02 | Open news details page | Medium | News visible | 1. Click details | News details page opens |

---

## UI Tests

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| NEWS-UI-01 | Validate news card layout | Low | News visible | 1. Observe card | Card displayed correctly |

---

## Edge Tests

| TC ID | Title | Priority | Pre-Conditions | Steps | Expected Results |
|------|------|------|------|------|------|
| NEWS-EDGE-01 | No news available | Low | No news published | 1. Scroll to news | System shows empty state |
