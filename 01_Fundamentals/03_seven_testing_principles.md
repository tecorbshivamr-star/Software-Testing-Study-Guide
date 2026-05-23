# The 7 Principles of Software Testing

> These principles were established by the **ISTQB** and form the foundation of all professional testing practices.

---

## Principle 1: Testing Shows the Presence of Defects

**Testing can show that defects are present, but cannot prove that there are no defects.**

Even after extensive testing, it is impossible to guarantee that software is bug-free. Testing reduces the probability of undiscovered defects but doesn't eliminate the risk entirely.

> **Example:** You tested 1000 test cases and all passed. This doesn't mean the software is bug-free — untested paths may still have bugs.

---

## Principle 2: Exhaustive Testing Is Impossible

**Testing everything is not feasible** (except for trivial cases). Instead of exhaustive testing, we use **risk analysis** and **priorities** to focus testing efforts.

> **Example:** A login form with just 3 fields (email, password, remember_me) has millions of possible input combinations. We use Equivalence Partitioning to reduce test cases to a manageable set.

---

## Principle 3: Early Testing Saves Time and Money

**Testing should start as early as possible** in the Software Development Life Cycle (SDLC). Finding and fixing bugs early is significantly cheaper than fixing them in production.

### Cost of Defect by Phase

| Phase Found | Relative Cost to Fix |
|-------------|---------------------|
| Requirements | 1x |
| Design | 5x |
| Development | 10x |
| Testing | 20x |
| Production | 100x+ |

> **Example:** A missing requirement found during review costs 1 hour to fix. The same issue found in production may cost weeks of hotfixes, rollbacks, and customer communication.

---

## Principle 4: Defect Clustering

**A small number of modules contain most of the defects.** Defects tend to cluster in specific high-risk areas of the software.

This is related to the **Pareto Principle (80/20 Rule)**: 80% of bugs are found in 20% of the code.

> **Example:** In an e-commerce app, the checkout and payment modules consistently have the most defects. Testing effort should be concentrated there.

---

## Principle 5: Beware of the Pesticide Paradox

**If the same tests are repeated over and over, they will eventually stop finding new bugs.** Test cases need to be reviewed and updated regularly to remain effective.

> **Example:** Running the same regression suite for 6 sprints finds fewer bugs each time. New test cases covering new features and edge cases must be added continuously.

---

## Principle 6: Testing Is Context-Dependent

**Testing is done differently in different contexts.** Safety-critical software (medical, aerospace) is tested differently from an e-commerce website.

| Context | Testing Approach |
|---------|-----------------|
| Banking app | Security + accuracy + compliance first |
| E-commerce | Performance + usability + payment flow |
| Medical device | Safety-critical, regulatory compliance (FDA) |
| Mobile game | Compatibility + performance + UX |
| Startup MVP | Speed over thoroughness |

---

## Principle 7: Absence-of-Errors Fallacy

**Finding and fixing defects does not help if the system is unusable or doesn't meet business requirements.** A bug-free system that doesn't solve the user's problem is still a failed system.

> **Example:** A banking app with zero bugs but a confusing, unusable UI will still fail in the market. Quality includes usability, not just defect-free code.

---

## Quick Revision Summary

| # | Principle | One Line |
|---|-----------|---------|
| 1 | Testing shows presence of defects | Can't prove zero bugs |
| 2 | Exhaustive testing impossible | Use risk & priority |
| 3 | Early testing saves cost | Shift-left approach |
| 4 | Defect clustering | 80% bugs in 20% code |
| 5 | Pesticide paradox | Update test cases regularly |
| 6 | Context-dependent | No one-size-fits-all |
| 7 | Absence-of-errors fallacy | Usability matters too |

---

*Next → [Verification vs Validation](./04_verification_vs_validation.md)*
