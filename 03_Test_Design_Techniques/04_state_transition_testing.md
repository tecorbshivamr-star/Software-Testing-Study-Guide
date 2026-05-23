# State Transition Testing

## What is State Transition Testing?
**State Transition Testing** is a black-box test design technique used when the system's behavior changes depending on its **current state** and the **events** that occur.

> *"If a system's output depends not just on input, but on history (its state), use State Transition Testing."*

---

## Key Terms
- **State:** The current condition of the system (e.g., Logged Out, Logged In, Locked).
- **Transition:** The change from one state to another.
- **Event:** The trigger that causes a transition (e.g., Entering wrong password).
- **Action:** The system response to an event (e.g., Lock account).

---

## State Transition Diagram: User Account Login

```
           [ Logged Out ]
                 │
           (Correct Pass)
                 │
                 ▼
            [ Logged In ]
```

What if they fail?

```
                      ┌───────────────┐
                      │  Logged Out   │ ◄───────────┐
                      └───────┬───────┘             │
                              │                     │
                    (Wrong Pass 1st Try)   (Wrong Pass 2nd Try)
                              │                     │
                              ▼                     │
                      ┌───────────────┐             │
                      │  1st Failure  ├─────────────┘
                      └───────┬───────┘
                              │
                    (Wrong Pass 3rd Try)
                              │
                              ▼
                      ┌───────────────┐
                      │    Locked     │
                      └───────────────┘
```

---

## State Transition Table

| Current State | Event (Input) | Expected Action | Next State |
|---|---|---|---|
| Logged Out | Correct Password | Login successful | Logged In |
| Logged Out | Wrong Password (1) | Error message | 1st Failure |
| 1st Failure | Correct Password | Login successful | Logged In |
| 1st Failure | Wrong Password (2) | Error message | Logged Out |
| Logged Out | Wrong Password (3) | Lock account | Locked |

---

## 📌 Key Takeaways
- Excellent for testing ATM transactions, UI wizard steps, game state levels, and authentication.
- Helps identify invalid/unwanted transitions (e.g., accessing checkout page when logged out).
- Guarantees complete coverage of state combinations.
