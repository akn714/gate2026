
## 📘 Summary: Regular Languages, Context-Free Grammars & Non-Context-Free Languages (TOC)

### 1️⃣ What is TOC?

**Theory of Computation (TOC)** is the study of:

- how computers understand languages
    
- what problems computers **can** and **cannot** solve
    

The “languages” here are **patterns of symbols**, not English.

---

### 2️⃣ What is a Context-Free Grammar (CFG)?

A **Context-Free Grammar** is a set of rules that tells how to **form valid strings**.

Example:

```
S → aSb
S → ab
```

This grammar generates:

```
ab, aabb, aaabbb
```

🔹 Called **context-free** because each rule works **independently**, without caring about surrounding symbols.

🔹 CFGs are used in:

- programming languages
    
- compilers
    
- syntax checking
    

---

### 3️⃣ What languages are **NOT context-free**?

Some languages are too complex for CFGs.

🔑 **Main limitation of CFGs**:

- Can match **one thing** (like aⁿ with bⁿ)
    
- Cannot match **two or more things at the same time**
    

#### Common NOT Context-Free Languages:

1. **{ aⁿ bⁿ cⁿ }**
    
    - equal number of a’s, b’s, and c’s
        
    - CFG can’t count all three together
        
2. __{ ww | w ∈ {a,b}_ }_*
    
    - same string repeated twice
        
    - CFG can’t remember and copy strings
        
3. **Languages needing multiple independent counts**
    

📌 These are proved using the **Pumping Lemma for CFLs**.

---

### 4️⃣ What are Regular Languages?

**Regular Languages** are the **simplest type of languages**.

They:

- are easy to recognize
    
- don’t need memory
    
- are handled by **Finite Automata**
    

#### Examples of Regular Languages:

- `{ a* }`
    
- `{ (ab)* }`
    
- strings ending with `b`
    

#### NOT Regular:

- `{ aⁿ bⁿ }`
    
- `{ aⁿ bⁿ cⁿ }`
    

Because:  
👉 Finite Automata **cannot count**

---

### 5️⃣ Relationship between language types

```
Regular Languages
⊂ Context-Free Languages
⊂ More powerful languages
```

|Type|Memory|Example|
|---|---|---|
|Regular|No memory|`(ab)*`|
|Context-Free|Stack memory|`aⁿ bⁿ`|
|Not CFL|Needs more power|`aⁿ bⁿ cⁿ`|

---

### 🔑 Final Takeaway

- **Regular Languages** → simple patterns, no counting
    
- **Context-Free Languages** → can count one thing
    
- **Not Context-Free Languages** → need multiple counts or copying
    

This progression explains **what computers can understand at different levels**.
