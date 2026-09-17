# 🐍 Python Practice Journey

This repository maps out my complete hands-on learning journey in Python. It contains structured topics, comprehensive definitions, conceptual explanations, and core code implementations. Click on any topic button below to expand its details.

---

## 📖 Python Basics

<details>
<summary><kbd> 📝 Click Here: Comments </kbd></summary>
<br>

### 📝 Notes & Explanation:
Comments are used to document code logic and improve readability. They are entirely ignored by the Python compiler during runtime.
* **Single-line Comment:** Formatted using the `#` symbol.
* **Multi-line Comment:** Formatted using triple quotes (`'''` or `"""`).
* **Purpose:** Helps developers collaborate and easily maintain code bases.

### 💻 Code Example:
```python
# This is a single-line comment
print("Hello World")  # Inline comment

"""
This is a multi-line comment.
We can write documentation or notes here.
"""
```
</details>

<details>
<summary><kbd> 📝 Click Here: Print Function </kbd></summary>
<br>

### 📝 Notes & Explanation:
The `print()` function sends formatted data to the standard output device (the screen).
* **Arguments:** It can take multiple objects separated by commas.
* **sep parameter:** Controls the separator string between objects (Default is a space).
* **end parameter:** Controls what prints at the end of the line (Default is a newline character `\n`).

### 💻 Code Example:
```python
print("Hello World!")
print("Apple", "Banana", sep=" - ")  # Outputs: Apple - Banana
print("Hello", end=" ")
print("Mama!")  # Outputs: Hello Mama!
```
</details>

<details>
<summary><kbd> 📝 Click Here: Escape Sequences </kbd></summary>
<br>

### 📝 Notes & Explanation:
Escape sequences embed special characters within text strings using a backslash (`\`).
* `\n`: New Line (Shifts subsequent text down one line).
* `\t`: Tab Space (Inserts 4 standard character spaces).
* `\'` and `\"`: Inserts raw quote symbols safely without terminating the string boundaries.

### 💻 Code Example:
```python
print("Hello\nMama")  # New Line
print("Name:\tRajasekhar")  # Tab Space
```
</details>

<details>
<summary><kbd> 📝 Click Here: Variables </kbd></summary>
<br>

### 📝 Notes & Explanation:
Variables function as named pointer allocations inside system memory to store data values.
* **Dynamic Typing:** Python explicitly determines data type scopes automatically during runtime based on variable values.
* **Re-assignment:** Variables can alter data sizes or shift underlying classes dynamically.

### 💻 Code Example:
```python
age = 36
gpa = 3.44
name = "Raja"
```
</details>

<details>
<summary><kbd> 📝 Click Here: Input Function </kbd></summary>
<br>

### 📝 Notes & Explanation:
The `input()` function pauses script execution to capture runtime data entered via a standard keyboard.
* **Default Data Type:** All values captured default exclusively to the String (`str`) class.
* **Typecasting:** Explicit data translation (such as wrapping with `int()` or `float()`) is required before running mathematical operations on numeric entries.

### 💻 Code Example:
```python
name = input("Enter name: ")
age = int(input("Enter age: "))  # Converting string data to integer
```
</details>

<details>
<summary><kbd> 📝 Click Here: How Python Code is Executed </kbd></summary>
<br>

### 📝 Notes & Explanation:
Python scripts pass through a highly systematic compilation and execution pipeline:
1. **Source Code (.py):** Readable programmatic commands authored by developers.
2. **Compilation Phase:** The local engine audits grammar syntax rules and builds compressed **Bytecode (.pyc)**.
3. **PVM Interpretation (Python Virtual Machine):** The internal engine evaluates bytecode layers line-by-line, converting blocks to binary **Machine Code (0s & 1s)** for direct CPU execution.
</details>

---

## 🔢 Data Types

<details>
<summary><kbd> 🔢 Click Here: Data Types & Categories </kbd></summary>
<br>

### 📝 Notes & Explanation:
Python stores structured data classes cleanly across fundamental architectural categories:
* **Numeric Type:** Houses numeric data points via integers (`int`), decimal points (`float`), and imaginary constants (`complex`).
* **Sequence Type:** Maps orderly, structured indexes like raw alphanumeric text (`str`), open lists (`list`), and rigid records (`tuple`).
* **Boolean Type:** Handles operational conditional choices utilizing primitive flags (`True` or `False`).

### 💻 Code Example:
```python
a = 10        # int
b = 5.5       # float
c = True      # bool
print(type(a)) # Looks up the class category
```
</details>

---

## ➕ Operators

<details>
<summary><kbd> ➕ Click Here: Arithmetic & Assignment Operators </kbd></summary>
<br>

### 📝 Notes & Explanation:
* **Arithmetic Operators:** Perform mathematical calculations (`+`, `-`, `*`, `/`, `//` for Floor Division, `%` for Modulus, `**` for Exponentiation).
* **Assignment Operators:** Assign values to variables, with shortcut variants that compute and update values in a single step (`=`, `+=`, `-=`, `*=`).

### 💻 Code Example:
```python
print(15 // 4)  # Floor division drops decimal remainders, outputting: 3
count = 5
count += 2      # Shortcut assignment updates count value to 7
```
</details>

<details>
<summary><kbd> ➕ Click Here: Comparison & Logical Operators </kbd></summary>
<br>

### 📝 Notes & Explanation:
* **Comparison Operators:** Evaluate relationships between items, returning Boolean outcomes (`==`, `!=`, `>`, `<`, `>=`, `<=`).
* **Logical Operators:** Evaluate and combine multiple conditional pathways systematically (`and`, `or`, `not`).

### 💻 Code Example:
```python
print(10 > 5 and 3 < 2) # True and False resolves explicitly to -> False
```
</details>

* ⬜ Identity Operators
* ⬜ Membership Operators
* ⬜ Bitwise Operators

---

## 🔀 Conditional Statements

<details>
<summary><kbd> 🔀 Click Here: if, if-else & Nested if </kbd></summary>
<br>

### 📝 Notes & Explanation:
Conditional control blocks execute specific pathways of code based on Boolean truth constraints.
* **if-elif-else:** Evaluates a series of conditions sequentially until one matches.
* **Nested if:** Evaluates a secondary condition branch inside a parent conditional branch.

### 💻 Code Example:
```python
score = 85
if score >= 90:
    print("Grade A")
elif score >= 75:
    print("Grade B")
else:
    print("Grade C")
```
</details>

---

## 🔁 For Loops

<details>
<summary><kbd> 🔁 Click Here: for Loop & Control Flow </kbd></summary>
<br>

### 📝 Notes & Explanation:
* **for Loop:** Iterates through items sequentially in a continuous sequence, collection, or a defined numerical span.
* **break:** Stops execution instantly and exits the active loop.
* **continue:** Skips the current iteration and jumps directly to the next cycle.
* **pass:** A null placeholder statement used to bypass empty block definitions safely.

### 💻 Code Example:
```python
for i in range(5):
    if i == 3:
        break
    print(i)
```
</details>

---

## ♾️ While Loops

<details>
<summary><kbd> ♾️ Click Here: while Loop & Control Flow </kbd></summary>
<br>

### 📝 Notes & Explanation:
A conditional block that loops continuously as long as its core state expression remains `True`. It immediately terminates the moment that expression evaluates to `False`.
</details>

---

## 📦 Data Structures
* ⬜ Strings
* ⬜ Lists
* ⬜ Tuples
* ⬜ Sets
* ⬜ Dictionaries

---

## ⚙️ Functions
* ⬜ Functions
* ⬜ Arguments
* ⬜ Return
* ⬜ Lambda
* ⬜ Recursion

---

## 🧱 Object-Oriented Programming (OOP)
* ⬜ Classes
* ⬜ Objects
* ⬜ Constructors
* ⬜ Inheritance
* ⬜ Polymorphism
* ⬜ Encapsulation
* ⬜ Abstraction
