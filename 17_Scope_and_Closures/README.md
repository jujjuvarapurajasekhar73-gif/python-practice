# 🔒 Module 17: Variable Scope & Functional Closures

This module covers Python's internal memory variable lookup hierarchies (LEGB Law), state modification override gateways (global & nonlocal), and advanced memory-retaining inner function architectures (Closures).

---

## 1. 🔒 The LEGB Scope Lookup Rule

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is Variable Scope?:** Scope defines exactly where a specific variable name box is visible and readable inside your application code layers.
* **The LEGB Law Hierarchy:** When you read a variable, Python searches 4 specific nested memory layers in strict sequential order. The moment it finds a match, it stops searching. If all 4 layers fail, it throws a `NameError` crash.

```text
🧠 Python LEGB Search Order Visual Map:
┌────────────────────────────────────────────────────────┐
│  B──> Built-in Scope (Python Internal Tools: len, print)│
│  ┌──────────────────────────────────────────────────┐  │
│  │  G──> Global Scope (Root level script variables)│  │
│  │  ┌──────────────────────────────────────────┐  │  │
│  │  │  E──> Enclosing Scope (Outer function block) │  │  │
│  │  │  ┌────────────────────────────────────┐  │  │  │
│  │  │  │  L──> Local Scope (Inner function) │  │  │  │
│  │  │  └────────────────────────────────────┘  │  │  │
│  │  └──────────────────────────────────────────┘  │  │
│  └──────────────────────────────────────────────────┘  │
└────────────────────────────────────────────────────────┘
```
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# 1. Global Scope layer allocation
data_metric = "GLOBAL_VALUE"

def outer_function():
    # 2. Enclosing Scope layer allocation
    data_metric = "ENCLOSING_VALUE"
    
    def inner_function():
        # 3. Local Scope layer allocation
        data_metric = "LOCAL_VALUE"
        
        # Python evaluates Local first, then Enclosing, then Global
        print(f"[LOOKUP] Target variable resolved to: {data_metric}")
        
    inner_function()

outer_function()
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
[LOOKUP] Target variable resolved to: LOCAL_VALUE
```
</details>

---

## 2. 🔒 The `global` Keyword Gateway

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **The Modifying Constraint:** By default, a function can freely *read* global variables, but it cannot *modify* or overwrite them. Attempting to change a global variable inside a function creates a brand new local box instead, leaving the original global box unchanged.
* **The `global` Declaration:** To explicitly modify a root-level variable from inside a sandboxed function, you must declare it using the `global` keyword statement row. This links the local thread directly to the master global memory block address slot.

```text
Visual Memory Modification Path:
Without global: [ global_var = 10 ] ───> function changes it ───> creates new [ local_var = 20 ]
With global:    [ global_var = 10 ] ───> function global_var ───> overwrites master [ global_var = 20 ]
```
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
system_balance = 5000 # Global variable initialization

def apply_transaction_override():
    global system_balance # Linking directly to the root global address box
    system_balance += 1500
    print(f"[INSIDE FUNCTION] Updated localized trace: {system_balance}")

print(f"[BEFORE FUNCTION] Global state balance:      {system_balance}")
apply_transaction_override()
print(f"[AFTER FUNCTION] Final committed master balance: {system_balance}")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
[BEFORE FUNCTION] Global state balance:      5000
[INSIDE FUNCTION] Updated localized trace: 6500
[AFTER FUNCTION] Final committed master balance: 6500
```
</details>

---

## 3. 🔒 The `nonlocal` Keyword Gateway

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **The Nested Isolation Problem:** In nested function architectures, an inner child function can read variables from its outer parent function (Enclosing scope), but it cannot directly modify them inline.
* **The `nonlocal` Solution:** Using `nonlocal` tells Python that the target variable belongs to the parent enclosing function's memory space, bypassing the local sandbox. It allows the inner function to mutate parent variables cleanly without creating new local duplicate registers.
* **Note:** `nonlocal` cannot be used to modify root-level global scope variables; it operates strictly inside nested enclosing function loops.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
def parent_orchestrator():
    active_connections = 10 # Enclosing variable scope allocation
    
    def child_worker():
        nonlocal active_connections # Targeting the enclosing parent scope box
        active_connections += 5
        print(f" -> Child worker mutated active count to: {active_connections}")
        
    child_worker()
    print(f"Parent orchestrator observes final count: {active_connections}")

print("Initiating Nested State Mutation Scan:")
parent_orchestrator()
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Initiating Nested State Mutation Scan:
 -> Child worker mutated active count to: 15
Parent orchestrator observes final count: 15
```
</details>

---

## 4. 🔒 Functional Closures (Advanced Memory Retention)

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is a Closure?:** A powerful structural technique where an inner nested function remembers and retains full access to the variables of its outer parent function, **even after the outer function has completely finished executing** and expired from the primary execution thread.
* **The Architecture Rule Checklist:**
  1. Must contain a nested inner function block structure layout.
  2. The inner function must read or reference at least one variable from the enclosing parent scope.
  3. The parent function must **return the inner function object itself as a reference** (without parenthesis execution markers).

```text
⚙️ Closure State Retention Model:
parent_run() ───> Enclosing variable = 100 ───> Function expires & leaves stack frame
               ───> Returns child object reference tracker
Returned child invoked ───> Remembers and securely reads parent variable (100)!
```
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
def secure_counter_generator(initial_count):
    # Enclosing scope variable tracking state allocation
    current_count = initial_count
    
    def increment_engine():
        nonlocal current_count
        current_count += 1
        return current_count
        
    return increment_engine # Returning function reference object without executing it

# Building an isolated persistent state instance tracker container box
my_counter_instance = secure_counter_generator(10)

# Invoking the closure object repeatedly shifts the sandboxed internal state value
print("Closure Execution Call Pass 1:", my_counter_instance())
print("Closure Execution Call Pass 2:", my_counter_instance())
print("Closure Execution Call Pass 3:", my_counter_instance())
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Closure Execution Call Pass 1: 11
Closure Execution Call Pass 2: 12
Closure Execution Call Pass 3: 13
```
</details>
