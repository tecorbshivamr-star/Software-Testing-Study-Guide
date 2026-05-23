# Cause-Effect Graphing

## What is Cause-Effect Graphing?
**Cause-Effect Graphing** is a black-box test design technique that uses a graphical representation to map the relationship between a given input (**Cause**) and its resulting output (**Effect**).

> *"Visualizing complex business logic to identify every combined scenario."*

---

## Key Terms
- **Cause:** A distinct input condition or precondition.
- **Effect:** The output result or action taken by the system.
- **Logic Gates:** Standard symbols (AND, OR, NOT) used to link causes and effects.

---

## Common Logical Operators in Graphing

```
      AND Gate (Both causes must be true)
      [ Cause 1 ] ──┐
                    ├── [ Effect ]
      [ Cause 2 ] ──┘
      
      OR Gate (At least one cause must be true)
      [ Cause 1 ] ──┐
                    ├── [ Effect ]
      [ Cause 2 ] ──┘
      
      NOT Gate (Inverse relationship)
      [ Cause 1 ] ───── [ Effect ]
```

---

## Steps to Apply Cause-Effect Graphing
1. **Identify Causes & Effects:** List all inputs and expected outputs from the requirements.
2. **Build the Graph:** Connect causes to effects using logical operators.
3. **Convert to Decision Table:** Transform the graph into a Decision Table.
4. **Generate Test Cases:** Write distinct test scripts for each rule in the table.

---

## 📌 Key Takeaways
- Ideal for complex rules where inputs interact heavily with each other.
- Provides a visual diagram that is easily understandable by both business and technical teams.
- Often serves as the intermediate step before producing a **Decision Table**.
