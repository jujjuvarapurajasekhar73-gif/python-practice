# 🐍 Python Practice Journey

ఈ రెపోజిటరీలో నా పైథాన్ లెర్నింగ్ జర్నీకి సంబంధించిన టాపిక్స్, వాటి నోట్స్, ఎక్స్‌ప్లనేషన్ మరియు ప్రాక్టీస్ కోడ్స్ అన్నీ అమర్చబడి ఉన్నాయి. కింద ఉన్న ఏ టాపిక్ బటన్ మీద క్లిక్ చేసినా దాని పూర్తి వివరాలు ఓపెన్ అవుతాయి.

---

## 📖 Python Basics

<details>
<summary><kbd> 📝 Click Here: Comments </kbd></summary>
<br>

### 📝 Notes & Explanation:
కామెంట్స్ అనేవి కోడ్ ఎందుకు రాశామో వివరించడానికి వాడతాం. ఇవి పైథాన్ కంపైలర్ ద్వారా రన్ అవ్వవు (Ignore అవుతాయి).
* **Single-line Comment:** ఒకే లైన్ కామెంట్ కోసం `#` వాడతాం.
* **Multi-line Comment:** ఎక్కువ లైన్ల కోసం ట్రిపుల్ కోట్స్ (`'''` లేదా `"""`) వాడతాం.

### 💻 Code Example:
```python
# This is a single-line comment
print("Hello World")  # Inline comment

"""
This is a multi-line comment.
We can write anything here.
"""
```
</details>

<details>
<summary><kbd> 📝 Click Here: Print Function </kbd></summary>
<br>

### 📝 Notes & Explanation:
స్క్రీన్ మీద అవుట్‌పుట్ డిస్‌ప్లే చేయడానికి `print()` ఫంక్షన్ వాడతాం. ఇందులో `sep` (separator) మరియు `end` పారామీటర్లను కూడా వాడవచ్చు.

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
స్ట్రింగ్స్ లోపల స్పెషల్ క్యారెక్టర్స్ (న్యూ లైన్, ట్యాబ్ స్పేస్) వాడటానికి ఇవి హెల్ప్ అవుతాయి.
* `\n`: New Line (కొత్త లైన్ లోకి వెళ్తుంది)
* `\t`: Tab Space (4 స్పేస్‌ల గ్యాప్ ఇస్తుంది)

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
డేటాను మెమరీలో స్టోర్ చేసుకోవడానికి వాడే కంటైనర్లను వేరియబుల్స్ అంటారు. పైథాన్ అనేది డైనమిక్ టైప్డ్ లాంగ్వేజ్, కాబట్టి డేటా టైప్ ముందుగా చెప్పక్కర్లేదు.

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
యూజర్ నుండి కీబోర్డ్ ద్వారా డేటా తీసుకోవడానికి `input()` వాడతాం. గమనిక: `input()` ఎప్పుడూ డేటాను 'String' రూపంలోనే తీసుకుంటుంది. నంబర్ కావాలంటే Typecasting చేయాలి.

### 💻 Code Example:
```python
name = input("Enter name: ")
age = int(input("Enter age: "))  # Converting string to integer
```
</details>

<details>
<summary><kbd> 📝 Click Here: How Python Code is Executed </kbd></summary>
<br>

### 📝 Notes & Explanation:
పైథాన్ కోడ్ బ్యాక్‌గ్రౌండ్‌లో ఎలా రన్ అవుతుందంటే:
1. **Source Code (.py):** మనం రాసే కోడ్.
2. **Compiler:** సోర్స్ కోడ్‌ను చెక్ చేసి **Bytecode (.pyc)** గా మారుస్తుంది.
3. **PVM (Python Virtual Machine):** ఈ బైట్‌కోడ్‌ను మెషిన్ లాంగ్వేజ్ (0s & 1s) లోకి మార్చి అవుట్‌పుట్ ఇస్తుంది.
</details>

---

## 🔢 Data Types

<details>
<summary><kbd> 🔢 Click Here: Data Types & Categories </kbd></summary>
<br>

### 📝 Notes & Explanation:
పైథాన్‌లో రకరకాల డేటా కేటగిరీలు ఉన్నాయి:
* **Numeric:** `int`, `float`, `complex`
* **Sequence:** `str`, `list`, `tuple`
* **Boolean:** `True` / `False`

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
* **Arithmetic:** `+`, `-`, `*`, `/`, `//` (Floor Division), `%` (Modulus), `**` (Exponent)
* **Assignment:** `=`, `+=`, `-=`, `*=`

### 💻 Code Example:
```python
print(15 // 4)  # Floor division gives 3
count = 5
count += 2      # count becomes 7
```
</details>

<details>
<summary><kbd> ➕ Click Here: Comparison & Logical Operators </kbd></summary>
<br>

### 📝 Notes & Explanation:
* **Comparison:** `==`, `!=`, `>`, `<`, `>=`, `<=` (True/False ఇస్తాయి)
* **Logical:** `and`, `or`, `not` (కండిషన్స్ కంబైన్ చేయడానికి)

### 💻 Code Example:
```python
print(10 > 5 and 3 < 2) # True and False -> False
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
కండిషన్స్ (నిబంధనలు) బట్టి నిర్ణయాలు తీసుకోవడానికి వాడతాం. ఒక కండిషన్ లోపల ఇంకో కండిషన్ పెడితే దాన్ని Nested `if` అంటారు.

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
* `for` లూప్ సీక్వెన్స్ మీద రన్ అవుతుంది.
* `break`: లూప్‌ను వెంటనే ఆపేస్తుంది.
* `continue`: కరెంట్ ఇటరేషన్ స్కిప్ చేస్తుంది.
* `pass`: ఖాళీ బ్లాక్ కోసం వాడతాం.

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
ఇచ్చిన కండిషన్ `True` గా ఉన్నంత సేపు ఈ లూప్ రన్ అవుతూనే ఉంటుంది. కండిషన్ `False` అయినప్పుడు ఆగుతుంది.
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

