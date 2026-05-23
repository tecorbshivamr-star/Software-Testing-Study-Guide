# Defect Lifecycle (Bug Lifecycle)

## What Is the Defect Lifecycle?

The **Defect Lifecycle** (also called **Bug Lifecycle**) is the complete journey a defect travels from the moment it is discovered to the moment it is closed. Every defect goes through a series of states managed by the QA and development teams.

---

## Defect States

```
         ┌──────────────────────────────────────┐
         │                                      │
       NEW → ASSIGNED → OPEN → FIXED → RETEST ─┤
         │                          │           │
         └── REJECTED    DEFERRED   └─ CLOSED   │
                                       ↑        │
                                  REOPENED ←────┘
```

---

## Each State Explained

| State | Who Sets It | Meaning |
|-------|-------------|---------|
| **New** | QA Engineer | Defect just logged, not yet reviewed |
| **Assigned** | QA Lead/Manager | Defect assigned to a developer |
| **Open** | Developer | Developer acknowledged and started working |
| **Fixed** | Developer | Code fix applied, ready for retest |
| **Retest** | QA Engineer | QA retesting the fix |
| **Closed** | QA Engineer | Fix verified, defect resolved |
| **Reopened** | QA Engineer | Fix didn't work, defect still exists |
| **Rejected** | Developer/Lead | Not a bug, or working as designed |
| **Deferred** | Manager/PO | Valid bug but fix postponed to next sprint |
| **Duplicate** | QA Lead | Same bug already reported |
| **Cannot Reproduce** | Developer | Unable to reproduce using given steps |

---

## Defect Lifecycle Flow (Detailed)

```
1. QA finds bug → Logs it as NEW
         ↓
2. QA Lead reviews → Assigns to Developer (ASSIGNED)
         ↓
3. Developer accepts → Starts work (OPEN)
         ↓
4. Developer fixes code → Marks as FIXED
         ↓
5. QA retests the fix (RETEST)
         ↓
    Fix works? ─YES→ Mark as CLOSED ✅
         ↓NO
    Mark as REOPENED → Back to Developer
```

---

## Severity vs Priority

These are two different dimensions of a defect:

### Severity
**Impact of the bug on the application.**

| Severity | Definition | Example |
|----------|-----------|---------|
| **Critical/Blocker** | App crashes, data loss, complete feature broken | Login doesn't work at all |
| **High/Major** | Major feature broken, no workaround | Payment fails intermittently |
| **Medium** | Feature partially broken, workaround exists | Search filters don't sort correctly |
| **Low/Minor** | UI issue, cosmetic defect | Button color slightly off |

### Priority
**How urgently the bug should be fixed.**

| Priority | Definition | Example |
|----------|-----------|---------|
| **P1 - Critical** | Fix immediately (same day) | Production is down |
| **P2 - High** | Fix in current sprint | Login broken in QA |
| **P3 - Medium** | Fix in next sprint | Minor feature issue |
| **P4 - Low** | Fix when time permits | Cosmetic issue |

### Interesting Combinations

| Scenario | Severity | Priority | Example |
|----------|----------|----------|---------|
| High severity, High priority | 🔴 | P1 | Payment crashes |
| High severity, Low priority | 🔴 | P4 | Bug in rarely used admin report |
| Low severity, High priority | 🟢 | P1 | CEO's name spelled wrong on homepage |
| Low severity, Low priority | 🟢 | P4 | Tooltip text typo |

---

## How to Write a Good Bug Report

A great bug report has:

```
Title: [Clear, specific, one-line description]
Example: "Login fails with 500 error for accounts with special chars in email"

Environment: Browser, OS, Build, URL
Severity: Critical / High / Medium / Low
Priority: P1 / P2 / P3 / P4
Steps to Reproduce:
  1. Navigate to /login
  2. Enter email: user+test@example.com
  3. Enter valid password
  4. Click Login
Expected Result: User redirected to dashboard
Actual Result: 500 Internal Server Error displayed
Attachments: screenshot.png, console_log.txt
```

---

## 📌 Key Takeaways

- Every organization has its own **defect workflow** (Jira, Azure DevOps, TestRail)
- **Severity** = impact on app | **Priority** = urgency to fix (they can differ!)
- A good bug report **can be reproduced by anyone** who reads it
- **Reopened** bugs count against developer quality metrics — first-fix quality matters
- **Deferred** bugs must be tracked and revisited in the next release

---

*Template → [Bug Report Template](./templates/bug_report_template.md)*  
*Related → [Jira Bug Reporting Guide](./06_jira_bug_reporting_guide.md)*
