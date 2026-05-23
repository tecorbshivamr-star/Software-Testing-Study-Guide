# Kanban for QA

Kanban is a highly visual framework designed to optimize work flow and maximize efficiency through **continuous delivery**.

---

## Key Kanban Principles for QA

### 1. Visualizing the Workflow
The Kanban board must show exactly where testing sits in the stream. A typical Kanban board looks like:

```
[ To Do ] ──→ [ In Dev ] ──→ [ Ready for QA ] ──→ [ In QA ] ──→ [ Done ]
```

### 2. Work in Progress (WIP) Limits
WIP limits prevent bottlenecks. If the `In QA` column has a WIP limit of **3**, the team cannot push more stories to `Ready for QA` until QA completes some testing and moves them to `Done`.

```
  [ In Dev ]        [ In QA ] (WIP Limit: 3)       [ Done ]
┌────────────┐     ┌───────────┐                 ┌──────────┐
│  Story A   │     │  Story B  │                 │ Story E  │
│  Story F   │     │  Story C  │                 │          │
└────────────┘     │  Story D  │                 └──────────┘
                   └───────────┘
                 (Max capacity!)
```

*If Story F is done coding, the developer must help test Story B, C, or D instead of starting new code.*

### 3. Managing Flow (Continuous Testing)
Instead of waiting for a batch release, QA pulls individual cards the second they enter `Ready for QA`, tests them, and pushes them straight to production or staging.

---

## 📌 Key Takeaways
- Kanban is **pull-based**, whereas Scrum is commitment-based.
- **WIP limits** are QA's best friend—they prevent devs from piling unchecked code on QA at the last minute.
- Forces the entire team to take ownership of quality when bottlenecks occur.
