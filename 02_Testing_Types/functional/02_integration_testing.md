# Integration Testing

## What is Integration Testing?
**Integration Testing** is the level of testing where individual software modules are combined and tested as a group. Its purpose is to expose faults in the interaction and interface between integrated units.

> *"Individual blocks might work perfectly, but do they fit together seamlessly?"*

---

## Integration Strategies

### 1. Big Bang Integration
All or most of the developed modules are coupled together to form a complete system, and then tested.
- **Pros:** Simple for small systems.
- **Cons:** High risk, extremely difficult to isolate bugs.

### 2. Top-Down Integration
Testing takes place from top to bottom, following the control flow. Lower-level modules are simulated using **Stubs**.
- **Stub:** A dummy module that simulates the behavior of a lower-level module.

### 3. Bottom-Up Integration
Testing takes place from bottom to top. High-level modules are simulated using **Drivers**.
- **Driver:** A dummy module that simulates the behavior of a higher-level module (invokes the code under test).

### 4. Sandwich/Hybrid Integration
Combines Top-Down and Bottom-Up approaches to test both layers simultaneously.

---

## Stubs vs Drivers Example

```
      [Main Module (Control)]  ← Top Level
             │
      ┌──────┴──────┐
  [Module A]    [Module B]     ← Mid Level
     │
  [Module C]                   ← Bottom Level (Lowest)
```

- If testing **Main Module** without Module A or B: You need **Stubs** (dummies underneath).
- If testing **Module C** without Module A: You need a **Driver** (dummy above to call C).

---

## 📌 Key Takeaways
- Focuses purely on communication protocols, data formats, and API interactions.
- Prevents database integrity issues and API handshake failures.
- Crucial before moving to the system-wide validation layer.
