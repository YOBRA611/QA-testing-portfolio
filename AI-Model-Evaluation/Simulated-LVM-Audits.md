# Simulated AI Model Evaluation (LVM Audit)

**DISCLAIMER:** *To adhere to Non-Disclosure Agreements (NDAs), these examples are simulated scenarios created to demonstrate my evaluation methodology. No proprietary client data or images are used in these reports.*

---

### Audit Case 01: Multi-Constraint Fidelity
**Prompt:** "A photo of a blue coffee mug on a wooden desk, next to a black laptop. There should be a small green plant in the background."

**AI Output Description:** "The image features a blue mug on a desk with a laptop. A red flower is visible in the background."

**Audit Results:**
* **Rating:** 🔴 **Fail**
* **Failure Mode:** Object Hallucination & Constraint Violation.
* **Metacognitive Trace:** The model correctly identified the mug and laptop but failed the background constraint. It hallucinated a "red flower" when a "small green plant" was specifically requested.

---

### Audit Case 02: Spatial Reasoning & Counting
**Prompt:** "An image of a kitchen counter with exactly three oranges and one silver knife to the left of the fruit."

**AI Output Description:** "I see a kitchen counter with four oranges and a silver knife on the right side."

**Audit Results:**
* **Rating:** 🔴 **Fail**
* **Failure Mode:** Counting Error & Spatial Logic Failure.
* **Metacognitive Trace:**
    1. **Counting:** The model failed the quantity constraint (Identified 4 oranges instead of 3).
    2. **Spatial Logic:** The model failed the positional constraint (Placed the knife on the 'right' instead of the 'left').

---

### Audit Case 03: Text Recognition (OCR) Accuracy
**Prompt:** "Describe the sign held by the man in the image."
**Image Context:** A man holding a sign that says: "DEALS EXPIRE TODAY."

**AI Output Description:** "The man is holding a sign that says 'DEALS EXPIRE TOMORROW'."

**Audit Results:**
* **Rating:** 🟡 **Partial Pass (Fair)**
* **Failure Mode:** Optical Character Recognition (OCR) Hallucination.
* **Metacognitive Trace:** The model accurately identified the context and the majority of the text but substituted the final word ("Today" vs "Tomorrow"). In high-stakes data labeling, this is a critical accuracy failure.

---

### 🛡️ Evaluation Methodology
When auditing Large Vision Models (LVMs), I apply the following three-step rubric:
1.  **Prompt Fidelity:** Does the image/description meet every single keyword in the prompt?
2.  **Visual Hallucinations:** Does the model invent objects or text that do not exist in the source?
3.  **Logical Consistency:** Does the spatial arrangement make sense (gravity, depth, orientation)?
