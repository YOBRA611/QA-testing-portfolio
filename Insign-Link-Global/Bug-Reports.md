**Insign Link Global Connect: QA Audit Report**

**ILG-001:** Missing Validation on "Phone Number" field

**Severity:** 🔴 High

**Description:** The "Phone" field in the booking form allows users to submit text instead of numbers.

**Actual Result:** Users can submit the form with "N/A" or "Call me," which breaks the automated SMS notification system.

**Expected Result:** The field should enforce a numeric pattern check.

**ILG-002:** Contact Form "Message" area has no character limit

**Severity:** 🟡 Low

**Description:** Users can paste an unlimited amount of text into the message box.

**Actual Result:** Massive text entries cause the email layout to break and can lead to database performance issues.
