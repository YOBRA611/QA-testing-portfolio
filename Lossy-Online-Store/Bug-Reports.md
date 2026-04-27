**Lossy Online Stores: QA Audit Report**

**🛒 E-commerce & Payment Logic**

**LOS-001:** Cart Quantity Manual Bypass

**Severity:** 🟠 High

**Category:** Functional Logic

**Description:** While the UI buttons prevent negative numbers, a user can manually type a negative integer (e.g., -5) into the quantity input box on the cart page.

**Actual Result:** The cart subtotal reflects a negative balance, potentially allowing a user to checkout with a reduced or zero total.

**Expected Result:** Input validation should force the value to a minimum of 1 upon any manual change.


**LOS-002:** M-Pesa Session Timeout Handling

**Severity:** 🟠 High

**Category:** Payment Integration

**Description:** If a user initiates an M-Pesa transaction but cancels the STK push on their phone, the order remains "Pending" in the system indefinitely.

**Actual Result:** Stock is reserved for "Ghost Orders," leading to inaccurate inventory levels for other customers.

**Expected Result:** The system should implement a 5-minute timeout that auto-cancels the order and releases stock if the payment callback isn't received.
