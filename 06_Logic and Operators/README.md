# 🎛️ Module 05: Logic & Operators

This module covers Python's operational control flow decision pipelines, truth value conditional evaluations, binary comparison boundaries, logical connecting gates, and memory-address identity checks.

---

## 1. 🎛️ Control Flow & Working with Booleans

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **Control Flow:** The logical order in which a computer executes individual statement lines inside a code file. Operators and logic allow us to build dynamic branches instead of simple straight execution.
* **`bool` (Boolean):** A core data type representing logical evaluations that resolve strictly to one of two binary status points: **`True`** or **`False`**. They act as the absolute foundation for all system decisions.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Instantiating primitive boolean flags to monitor system state parameters
is_firewall_active = True
is_system_overloaded = False

print(f"Active Firewall Security Flag Status: {is_firewall_active} -> {type(is_firewall_active)}")
print(f"Active Overhead Alert Flag Status:    {is_system_overloaded} -> {type(is_system_overloaded)}")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Active Firewall Security Flag Status: True -> <class 'bool'>
Active Overhead Alert Flag Status:    False -> <class 'bool'>
```
</details>

---

## 2. 🎛️ Comparison Operators (Relational Boundaries)

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

Comparison operators audit numeric or text values against each other and return a clean boolean result (`True` or `False`):
* `==` ──> **Equal to**: Checks if two values match perfectly.
* `!=` ──> **Not equal to**: Returns `True` if values do not match.
* `>`  ──> **Greater than**: Checks if the left number exceeds the right number.
* `<`  ──> **Less than**: Checks if the left number is smaller than the right number.
* `>=` ──> **Greater than or equal to** boundary check.
* `<=` ──> **Less than or equal to** boundary check.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
current_active_connections = 45
max_allowed_threshold = 50

# Executing structural relational comparison passes
is_below_limit = current_active_connections < max_allowed_threshold
is_at_capacity = current_active_connections == max_allowed_threshold

print(f"Is connection status within safe bounds?: {is_below_limit}")
print(f"Is system running at maximum peak capacity?:   {is_at_capacity}")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Is connection status within safe bounds?: True
Is system running at maximum peak capacity?:   False
```
</details>

---

## 3. 🎛️ Logical Operators (`and`, `or`, `not`) & Execution Order

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

Logical operators are used to connect multiple comparison conditions together to build complex business rules:
* **`and` Gate:** Returns `True` **only** if every single condition evaluates to `True` simultaneously.
* **`or` Gate:** Returns `True` if **at least one** independent condition evaluates to `True`.
* **`not` Operator:** Acts as an inverter. It flips a boolean state to its exact opposite (`True` becomes `False`, and vice versa).

```text
📊 System Truth Logic Reference Table:
 ┌─────────┬─────────┬─────────────┬────────────┐
 │ Cond A  │ Cond B  │  A and B    │   A or B   │
 ├─────────┼─────────┼─────────────┼────────────┤
 │  True   │  True   │    True     │    True    │
 │  True   │  False  │    False    │    True    │
 │  False  │  False  │    False    │    False   │
 └─────────┴─────────┴─────────────┴────────────┘
```
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Simulating a multi-tier authorization security check routine
has_valid_auth_token = True
has_admin_clearance = False
is_account_suspended = False

# 1. Evaluating an 'and' logic boundary matrix pass
can_modify_database = has_valid_auth_token and has_admin_clearance

# 2. Combining 'or' and 'not' logic blocks with standard operator order evaluation
is_access_granted = (has_valid_auth_token or has_admin_clearance) and not is_account_suspended

print(f"Database Modification Rights Approved: {can_modify_database}")
print(f"Final System Gateway Access Granted:   {is_access_granted}")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Database Modification Rights Approved: False
Final System Gateway Access Granted:   True
```
</details>

---

## 4. 🎛️ Membership Operators (`in`, `not in`)

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is it?:** Specialized sequence scanners used to check if a target value exists inside a larger multi-value collection (like lists, tuples, or text strings).
* **Operators Matrix:**
  * `in` ──> Yields `True` if the item is found inside the array sequence.
  * `not in` ──> Yields `True` if the target item is missing from the container pool.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Initializing an environment registry mapping pool list container
blacklisted_malicious_ips = ["192.168.1.99", "10.0.0.5", "172.16.0.4"]
incoming_client_ip = "10.0.0.5"

# Auditing element presence using membership arrays
is_threat_detected = incoming_client_ip in blacklisted_malicious_ips
print(f"Security Alert: Is incoming client blacklisted?: {is_threat_detected}")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Security Alert: Is incoming client blacklisted?: True
```
</details>

---

## 5. 🎛️ Identity Operators (`is`, `is not`) vs Value Equality (`==`)

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

This separates value verification from actual computer hardware address checks:
* **`==` (Value Equality):** Audits if two separate data variables contain the **same value** content.
* **`is` (Identity Check):** Audits if two variables point to the **exact same memory location address** slot in computer RAM.

```text
🧠 Visual Identity Location Tracking Model:
Variable X ───> [ Memory Block Location #7300 ] ───> Contains Data: [1, 2]
Variable Y ───> [ Memory Block Location #7300 ] ───> Points to exact same box (is = True)
Variable Z ───> [ Memory Block Location #9999 ] ───> Contains same data [1, 2] but separate box (== is True, is = False)
```
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Initializing two distinct, separate array objects containing matching values
node_pool_alpha = [1, 2, 3]
node_pool_bravo = [1, 2, 3]

# Mapping variable references to point directly to the exact same memory box block
node_pool_charlie = node_pool_alpha

print("Value Check Equality test (alpha == bravo):", node_pool_alpha == node_pool_bravo)
print("Memory Space Identity test (alpha is bravo):", node_pool_alpha is node_pool_bravo)
print("Memory Space Identity test (alpha is charlie):", node_pool_alpha is node_pool_charlie)
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Value Check Equality test (alpha == bravo): True
Memory Space Identity test (alpha is bravo): False
Memory Space Identity test (alpha is charlie): True
```
</details>
