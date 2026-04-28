**Pearls & Psalms Hospital: QA Audit Report**

**Focus:** Appointment Booking & Contact Form

**PPH-001:** Appointment Form bypasses "Required" fields

**Severity:** 🔴 High

**Description:** The "Doctor Specialty" dropdown is marked as required, but the form allows submission even if no option is selected.

**Actual Result:** Blank appointments are sent to the hospital database, making it impossible for staff to prepare.

**Evidence:**
![Screenshot of Date Picker Error](./images/past-date-error.png)

**Expected Result:** Form should trigger a "Please select a specialty" error message.

**PPH-002:** Success message appears, but email fails to send

**Severity:** 🟠 Medium

**Description:** Upon submitting the Contact Form, a "Thank You" message appears, but the Network tab in DevTools shows a 500 Internal Server Error.

**Observation:** The user thinks they contacted the hospital, but the message was never delivered.


