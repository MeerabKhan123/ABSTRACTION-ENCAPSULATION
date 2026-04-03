# Python OOP — Complete Reference

![Python](https://img.shields.io/badge/Python-3.x-3776ab?style=flat-square&logo=python&logoColor=white)
![Topics](https://img.shields.io/badge/Topics-OOP%20%7C%20Encapsulation%20%7C%20Abstraction-success?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-informational?style=flat-square)

> Encapsulation · Abstraction · Abstract Classes · Access Modifiers — demonstrated through real-world class examples.

---

## Table of Contents

- [Core Concepts](#core-concepts)
- [Project Structure](#project-structure)
- [Class Demos](#class-demos)
- [Theory Q&A](#theory-qa)
- [How to Run](#how-to-run)

---

## Core Concepts

| Concept | Tool | Purpose |
|---|---|---|
| **Encapsulation** | `__private` variables | Protects data; access only via methods |
| **Abstraction** | `ABC` + `@abstractmethod` | Hides implementation; exposes interface |
| **Abstract Classes** | `from abc import ABC` | Blueprint — cannot be instantiated directly |
| **Access Modifiers** | `__var` → `_Class__var` | Python name-mangling for private access |

---


## Class Demos

<details>
<summary><strong>BankAccount</strong> — Encapsulation with <code>__balance</code></summary>

```
Deposited 500. New balance: 1500
Withdrawn 200. Remaining: 1300
Insufficient balance!
Balance: 1300
```
</details>

<details>
<summary><strong>Student</strong> — Marks validation</summary>

```
Marks set to: 85
Invalid! Marks must be between 0 and 100.
Marks: 85
```
</details>

<details>
<summary><strong>Password Manager</strong> — Secure __password access</summary>

```
Password updated successfully.
Wrong password!
Password is correct!
```
</details>

<details>
<summary><strong>Employee</strong> — Salary with raise logic</summary>

```
Salary: 50000
Salary after 10% increase: 55000.0
Percent cannot be negative!
```
</details>

<details>
<summary><strong>Abstract Shape</strong> — Rectangle & Circle</summary>

```
Rectangle Area: 15
Circle Area: 153.86
```
</details>

<details>
<summary><strong>ATM Machine</strong> — Full simulation</summary>

```
Current Balance: 10000
Deposited 2000. Balance: 12000
Withdrawn 5000. Balance: 7000
Insufficient funds!
```
</details>

---

## Theory Q&A

<details>
<summary><strong>1. What is Encapsulation?</strong></summary>

Wrapping data (variables) and methods together in a class, and restricting direct access to private data. Access is only through defined getter/setter methods.

</details>

<details>
<summary><strong>2. What is Abstraction?</strong></summary>

Hiding complex implementation details and exposing only essential features. Achieved using Python's `ABC` module and `@abstractmethod` decorator.

</details>

<details>
<summary><strong>3. Abstraction vs Encapsulation?</strong></summary>

| | Encapsulation | Abstraction |
|---|---|---|
| **Hides** | Data (private variables) | Implementation (abstract methods) |
| **Tool** | `__variable` | `ABC`, `@abstractmethod` |
| **Goal** | Security | Simplicity |

**Car analogy:**
- Encapsulation → engine parts hidden inside the car body *(data hiding)*
- Abstraction → driver uses steering/pedals without knowing how the engine works *(implementation hiding)*

</details>

<details>
<summary><strong>4. What is a Private Variable in Python?</strong></summary>

A variable with a `__` (double underscore) prefix, e.g. `__balance`. Python name-mangles it to `_ClassName__balance`. Direct outside access raises `AttributeError`.

</details>

<details>
<summary><strong>5. What is an Abstract Class?</strong></summary>

A class that **cannot be instantiated** directly. It has at least one `@abstractmethod` that every child class must override.

```python
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def area(self):
        pass
```

</details>

<details>
<summary><strong>6. Instance Attribute vs Class Attribute?</strong></summary>

| | Instance | Class |
|---|---|---|
| **Defined in** | `__init__` | Outside `__init__` |
| **Belongs to** | Each object separately | All objects (shared) |
| **Change affects** | Only that object | All objects |

</details>

<details>
<summary><strong>7. Role of self?</strong></summary>

- Refers to the current object calling the method
- Required so each object accesses its own data
- `self` is **not a keyword** — just a strong convention
- Without it, Python cannot find the object's attributes

</details>

<details>
<summary><strong>8. Edge cases — what happens if...?</strong></summary>

| Scenario | Result |
|---|---|
| No `__init__` defined | Python uses default constructor; object created but no custom attributes |
| `obj.__balance` accessed directly | `AttributeError` — name-mangled to `_ClassName__balance` |
| Instantiate an abstract class | `TypeError`: cannot instantiate abstract class with abstract method |

</details>

---

## How to Run

```bash
# Clone the repository
git clone https://github.com/your-username/python-oop.git
cd python-oop

# Run all demos — no external dependencies required
python main.py
```

**Requirements:** Python 3.x — standard library only.

---

## Key Takeaways

- Use **encapsulation** to protect sensitive data (passwords, balances, salaries)
- Use **abstraction** to define a common interface for related classes
- **Private variables** (`__var`) enforce controlled, validated access
- **Abstract classes** act as contracts — all child classes must implement defined methods
- `self` is the backbone of OOP in Python — it connects every method to its object
