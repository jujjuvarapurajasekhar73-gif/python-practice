# 🗂️ Module: Data Types Foundations

This module covers Python's data sorting classification layers, dynamic runtime type detection mechanics, functional tool structures, and structural boundaries separating global functions from type-specific methods.

---

## 1. 🗂️ What is a Data Type & Dynamic Typing

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is a Data Type?:** A data type defines the kind of value a variable holds. It determines exactly what mathematical or logical operations you can perform on a value, protecting your code from wrong behaviors.
* **Dynamic Typing Benefit:** Python is dynamically typed. This means you do not declare variable types manually. Python automatically detects the data type at runtime based on the value assigned, and a variable's type can change freely whenever it is reassigned.

```text
Visual Run-Time Casing Logic:
a = 10     ───> [ Python auto-detects 'int'  ] ───> Math Allowed (10 + 5 = 15)
a = "Abc"  ───> [ Python auto-detects 'str'  ] ───> Text Operations Allowed (.upper())
```
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Demonstrating dynamic typing behavior changes inside the same variable slot
runtime_data_box = 100
print(f"Value: {runtime_data_box} | Automatically Detected Type: {type(runtime_data_box)}")

runtime_data_box = "Production-Tier"
print(f"Value: {runtime_data_box} | Automatically Detected Type: {type(runtime_data_box)}")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Value: 100 | Automatically Detected Type: <class 'int'>
Value: Production-Tier | Automatically Detected Type: <class 'str'>
```
</details>

---

## 2. 🗂️ Categories of Data Types (The Roadmap)

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

Python groups data values into three main structural categories based on how much data they hold in memory:
1. **No Value (`NoneType`):** Used when a variable exists, but there is simply no data inside it yet (it’s just empty). Represented by `None`.
2. **Single Value (Primitive Types):** This type holds one simple value at a time.
   * `int` ──> Whole numbers without decimals (e.g., `50`).
   * `float` ──> Numbers with fractional decimals (e.g., `3.14`).
   * `str` ──> Text values enclosed inside quotes (e.g., `"Hello"`).
   * `bool` ──> Logical states resolving only to `True` or `False`.
3. **Multi Values (Data Structures / Containers):** This type holds multiple grouped values together to keep them organized. Examples include `list` (arrays like `[1, 2, 3]`) and `dict` (key-value pairings).

```text
Visual Storage Basket Analogy:
 ┌───────────────┐      ┌───────────────┐      ┌───────────────┐
 │   No Value    │      │ Single Value  │      │  Multi Values │
 ├───────────────┤      ├───────────────┤      ├───────────────┤
 │   [ None ]    │      │  [ "Apple" ]  │      │ [1, 2, 3, 4]  │
 └───────────────┘      └───────────────┘      └───────────────┘
```
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Instantiating variables mapping across the 3 main categorical roadmap fields
empty_buffer_slot = None
single_metric_value = 15.75
multi_asset_collection = ["NODE-A", "NODE-B", "NODE-C"]

print(f"Category [No Value]: {empty_buffer_slot} -> {type(empty_buffer_slot)}")
print(f"Category [Single Value]: {single_metric_value} -> {type(single_metric_value)}")
print(f"Category [Multi Values]: {multi_asset_collection} -> {type(multi_asset_collection)}")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Category [No Value]: None -> <class 'NoneType'>
Category [Single Value]: 15.75 -> <class 'float'>
Category [Multi Values]: ['NODE-A', 'NODE-B', 'NODE-C'] -> <class 'list'>
```
</details>

---

## 3. 🗂️ Tools for Your Data: Functions vs Methods

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

To do something to your data, you use functions. These tools are organized inside Python's standard library and have different structural shapes:
* **Standalone Functions:** Independent reusable blocks of code that work globally across multiple data types. Values are passed explicitly into them as arguments. (e.g., `print(value)`, `type(value)`).
* **Methods of a Class:** Special type-specific tools that are tightly bound to a specific data object or class. They operate directly on the object they belong to using dot notation and cannot be used by other types. (e.g., `"hello".upper()`).
* **Operations:** Mathematical or logical symbols (like `+`, `-`, `>`, `==`) performing backend actions under the hood.

```text
Syntax Shape Structural Variance:
Global Function:  function_name( value )     ───> print("hi")
Class Method:     value.method_name()        ───> "hi".upper()
```
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# 1. Utilizing Standalone Functions (General independent tools)
raw_text_data = "enterprise_log_stream"
print("Length Calculation via Function:", len(raw_text_data))

# 2. Utilizing Object Class Methods (Type-specific tools)
transformed_text_data = raw_text_data.upper()
print("Case Transformation via Class Method:", transformed_text_data)

# Note: Trying to call 50.upper() would cause an immediate syntax crash
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Length Calculation via Function: 21
Case Transformation via Class Method: ENTERPRISE_LOG_STREAM
```
</details>

---

## 4. 🗂️ Data Types Examples & Challenge Verification

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **Operator Behavior Controls:** Data types dictate how operators act. For instance, using the `+` symbol on two integers calculates their math sum, while using it on two strings triggers concatenation (joining text pieces together).
* **System Safeguards:** Understanding data types prevents unexpected processing bugs and ensures calculations always return correct, reliable outcomes.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Unifying data tools into an operational verification block challenge
# Demonstrating how the same operator produces different results based on data types

# Case A: Integer types execution path (Adding numbers)
result_numeric_math = 2 + 3

# Case B: String types execution path (Joining text)
result_string_concatenation = "2" + "3"

print(f"Math Calculation (int + int) Output:  {result_numeric_math}")
print(f"Text Concatenation (str + str) Output: {result_string_concatenation}")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Math Calculation (int + int) Output:  5
Text Concatenation (str + str) Output: 23
```
</details>
