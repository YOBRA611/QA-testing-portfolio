**Lossy Online Stores: QA Audit Report**

**Focus:** Checkout Process & Contact Form

**LOS-001:** Checkout allows "Empty Cart" submission

**Severity:** 🔴 High

**Description:** If a user navigates directly to the checkout URL without adding products, the "Place Order" button remains active.

**Actual Result:** The system processes an order with a total of $0.00.

**Expected Result:** The checkout button should be disabled, and a "Your cart is empty" message should be displayed.

**LOS-002:** Contact Form "Email" field accepts invalid formats

**Severity:** 🟠 Medium

**Description:** The email input does not check for the @ symbol or a domain extension.

**Observation:** Users can submit "brian-at-gmail" as a valid email, preventing the store from replying to inquiries.
