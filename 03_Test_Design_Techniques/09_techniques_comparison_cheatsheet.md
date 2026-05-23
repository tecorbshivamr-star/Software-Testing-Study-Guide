# Test Design Techniques Comparison

| Technique | Category | Best Used For | Pros | Cons |
|---|---|---|---|---|
| **Equivalence Partitioning (EP)** | Black-box | Input ranges, dropdown selections | Drastically reduces test suite size | May miss boundary edge cases |
| **Boundary Value Analysis (BVA)** | Black-box | Numeric boundaries, character lengths | Catches off-by-one errors | Only applicable to ordered boundaries |
| **Decision Table** | Black-box | Complex logical conditions / business rules | Comprehensive combination coverage | Rapidly grows in size ($2^N$ combinations) |
| **State Transition** | Black-box | Authentication flows, sequential wizards | Excellent for sequential state flows | Difficult for stateless applications |
| **Use Case Testing** | Black-box | End-to-end user transactions | Verifies real-world business utility | Doesn't cover structural code branches |
| **Pairwise Testing** | Black-box | Configuration matrices (OS, browser, DB) | Reduces combinatorial explosion | Misses rare three-way parameter errors |
| **Error Guessing** | Experience | Ad-hoc validation, edge cases | Very fast, leverages human intuition | Unstructured, non-repeatable |
| **Statement Coverage** | White-box | Unit testing structural checks | Ensures every line of code runs at least once | Misses branch outcomes and loops |
| **Branch Coverage** | White-box | Unit testing conditional loops | Verifies all decision branches (True/False) | More complex to write |

---

## How to Select the Right Technique

```
Are there numeric ranges or sizes?
  ├── Yes ──→ Use EP + BVA
  └── No
       │
Are there multiple combined conditions?
  ├── Yes ──→ Use Decision Tables
  └── No
       │
Are there sequential phases/states?
  ├── Yes ──→ Use State Transition
  └── No ──→ Use Use Case Testing
```
