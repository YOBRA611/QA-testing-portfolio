**Functional Logic and Business Rules**

**PPH-001:** Appointment Form Allows Booking on Past Dates
**Severity:** 🔴 High
**Category:** Functional Logic
**Description:** The date picker on the "Book Appointment" form does not have a restriction preventing users from selecting dates that have already passed.
**Steps to Reproduce:** 
1. Navigate to the Appointment section.
2. Open the date picker/calendar.
3. Select a date from the previous month.
4. Fill in the required details and click "Submit."
**Actual Result:** The system accepts the entry and displays a "Booking Confirmed" message for a date in the past.
**Expected Result:** Dates before the current date should be disabled or greyed out in the UI.
**PPH-002:** Emergency Contact Field Lacks Numeric Validation
**Severity:** 🟡 Medium
**Category:** Data Integrity
**Description:** The "Emergency Phone Number" input field accepts alphabetic characters and symbols instead of enforcing a numeric-only format.
**Actual Result:** A user can submit the word "HELP" or "None" in the phone number field.
**Expected Result:** The field should only accept numeric input and validate for a standard phone number length.
