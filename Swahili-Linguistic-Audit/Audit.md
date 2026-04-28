# Swahili Linguistic Audit & AI Failure Mode Analysis

This document serves as a technical log for identifying, documenting, and correcting linguistic hallucinations and logical failures in Swahili Large Language Models (LLMs).

---

### Audit Case 01: Morphological Synthesis (Noun Class Agreement)
**Prompt:** Translate "The tall trees were cut" into Swahili.  
**Model Output:** *"Miti refu zilikatwa."*

**Expert Evaluation:**
* **Failure Mode:** Incorrect Noun Class (Ngeli) agreement.
* **Technical Trace:** The noun 'Miti' belongs to the **U-I (M-MI)** class. The adjective must take the prefix 'mi-' (mirefu) and the verb must take the subject prefix 'i-' (ilikatwa).
* **Root Cause:** The model is hallucinating rules from the **I-ZI** class (commonly used for 'N' class nouns like *Nyumba*) or **LI-YA** class.
* **Corrected Output:** *"Miti mirefu ilikatwa."*

---

### Audit Case 02: Semantic Pragmatics (Contextual Ambiguity)
**Prompt:** Translate "I am looking for a bank" (Context: A person standing by a river).  
**Model Output:** *"Natafuta benki."*

**Expert Evaluation:**
* **Failure Mode:** Lack of contextual pragmatics / Word Sense Disambiguation.
* **Technical Trace:** In Swahili, 'Benki' refers strictly to a financial institution. For a geographical feature like a river bank, the term is 'Kando' or 'Ukingo'. 
* **Metacognitive Note:** A high-fidelity model should ask for clarification or use the context to provide 'Ukingo wa mto.' Providing 'Benki' in a nature context is a logic failure.
* **Corrected Output:** *"Natafuta ukingo wa mto."*

---

### Audit Case 03: Syntactic Complexity (Subjunctive Mood)
**Prompt:** Translate "I want you to go to the market."  
**Model Output:** *"Nataka wewe unakwenda sokoni."*

**Expert Evaluation:**
* **Failure Mode:** Incorrect Mood (Indicative vs. Subjunctive).
* **Technical Trace:** The verb 'Nataka' (I want) triggers the **Subjunctive Mood** in the second verb. The model used the indicative 'unakwenda' (you are going).
* **Linguistic Rule:** The final vowel '-a' of the verb 'kwenda' must change to '-e', and the tense marker '-na-' must be dropped.
* **Corrected Output:** *"Nataka uende sokoni."*

---

### Summary of Expertise
Through these audits, I demonstrate:
1. **Error Traceability:** Identifying the specific grammatical rule being violated.
2. **Failure Mode Categorization:** Distinguishing between simple typos and deep logical/syntactic hallucinations.
3. **Reasoning Hardening:** Providing the "why" to help engineers adjust prompt weights and evaluation metrics.
