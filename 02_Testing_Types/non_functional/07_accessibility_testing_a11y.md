# Accessibility Testing (a11y)

## What is Accessibility Testing?
**Accessibility Testing** ensures that a software application (usually a website or mobile app) is usable by people with disabilities, including those with visual, auditory, physical, speech, cognitive, and neurological impairments.

*Note: It is often abbreviated as **a11y** (an "a", followed by 11 letters, followed by a "y").*

---

## Why is it Important?
1. **Inclusivity:** Ensures everyone has equal access to digital services.
2. **Legal Compliance:** Many countries have laws mandating web accessibility (e.g., ADA in the USA, EAA in Europe, Section 508 for US Federal agencies). Failure to comply can result in massive lawsuits.
3. **SEO:** Many accessibility best practices (like image alt tags and semantic HTML) directly improve search engine rankings.

---

## WCAG (Web Content Accessibility Guidelines)
The international standard for web accessibility. It is categorized into three conformance levels:
- **Level A:** Minimum level. Without this, the site is impossible for some users to access.
- **Level AA:** The standard target for most commercial and government websites.
- **Level AAA:** The highest and strictest level (often unnecessary for standard websites).

---

## Core Accessibility Checks

### 1. Visual Impairments (Blindness, Low Vision, Color Blindness)
- **Screen Reader Compatibility:** Can software like JAWS, NVDA, or Apple VoiceOver read the page logically?
- **Alt Text:** Do all meaningful images have descriptive `alt` tags?
- **Color Contrast:** Is the contrast ratio between text and background at least $4.5:1$ (WCAG AA standard)?
- **Color Reliance:** Is color the *only* way information is conveyed? (e.g., Error fields should be red *and* have an error icon/text).

### 2. Motor/Physical Impairments
- **Keyboard Navigation:** Can the entire application be navigated and operated using *only* the `Tab`, `Enter`, `Space`, and `Arrow` keys?
- **Focus Indicators:** Is it visually obvious which element currently has keyboard focus?

### 3. Auditory Impairments
- **Captions/Transcripts:** Do all videos have accurate closed captions?

---

## Accessibility Testing Tools
- **Automated Scanners:** Axe DevTools, Lighthouse, WAVE (Finds ~30% of issues like contrast and missing alt tags).
- **Screen Readers:** NVDA (Windows), VoiceOver (Mac/iOS).
- **Manual Checks:** Unplug the mouse and try to use the site.

---

## 📌 Key Takeaways
- Accessibility is not just a nice-to-have; it is a **legal requirement** for many businesses.
- Automation tools can only catch structural errors; manual testing with a keyboard and screen reader is mandatory.
