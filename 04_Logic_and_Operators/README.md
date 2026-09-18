# ➕ Module 4: Logic & Operators

This module covers control flow foundations, boolean evaluations, condition gates, execution prioritization rules, and advanced resource tracking utilizing membership and identity operations.

---

## 1. ➕ Control Flow & Working with Booleans

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is it?:** The strategic routing blueprint that dictates the exact order in which code lines are executed based on dynamic evaluation triggers.
* **Boolean Primitive States:** Controlled strictly by two unique absolute values: `True` and `False` (instantiated from `<class 'bool'>`). They act as the raw traffic lights for application control structures.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Initializing system core flag tracking variables
is_server_healthy = True
is_maintenance_mode = False

print(f"System Health Status: {is_server_healthy}")
print(f"Maintenance Activity Flag: {is_maintenance_mode}")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
System Health Status: True
Maintenance Activity Flag: False
```
</details>

---

## 2. ➕ Comparison Operators

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is it?:** Operational symbols used to evaluate values against one another to return a strict boolean state.
* **Core Comparison Flags:**
  * `==` (Equality Check): Confirms if the left value matches the right value.
  * `!=` (Inequality Check): Validates that the targets are completely distinct.
  * `>`, `<`, `>=`, `<=` (Relational Scaling): Audits size metrics and value ceilings.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Evaluating incoming server response thresholds
current_http_status = 200
active_cpu_utilization = 85

is_request_successful = (current_http_status == 200)
is_cpu_overloaded = (active_cpu_utilization >= 80)

print(f"Request Success Vector: {is_request_successful}")
print(f"Critical Overhead Breached: {is_cpu_overloaded}")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Request Success Vector: True
Critical Overhead Breached: True
```
</details>

---

## 3. ➕ Logical Operators (and, or, not) & Examples

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is it?:** Conditional gates used to merge multiple independent boolean parameters into a single final processing decision path.
* **The Logic Gate Matrix:**
  * `and`: Demands that every single evaluated parameter branch resolves as `True`. If even one item checks out as false, the entire gateway safely fails.
  * `or`: Requires that at least one single statement pathway evaluates to `True`.
  * `not`: A unary operator that completely flips the active logical state into its exact polar opposite.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Multi-layered infrastructure deployment access check routines
is_token_valid = True
is_ip_whitelisted = False
is_firewall_locked = True

# Evaluating traffic gateway compliance vectors
allow_standard_access = is_token_valid and is_ip_whitelisted
allow_admin_override = is_token_valid or is_ip_whitelisted
force_emergency_bypass = not is_firewall_locked

print(f"Standard Ingestion Pass: {allow_standard_access}")
print(f"Admin Escalation Pass: {allow_admin_override}")
print(f"Bypass Protocol Allowed: {force_emergency_bypass}")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Standard Ingestion Pass: False
Admin Escalation Pass: True
Bypass Protocol Allowed: False
```
</details>

---

## 4. ➕ Execution Order (Operator Precedence)

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is it?:** The evaluation hierarchy (the order of operations) that determines which mathematical and logical operators are computed first inside complex statements.
* **The Precedence Hierarchy:**
  1. Parentheses `()` always take highest priority.
  2. Arithmetic operators (like `**`, `*`, `/`, `+`, `-`).
  3. Comparison operators (like `==`, `!=`, `<`).
  4. Logical operators are processed in this exact sequence: `not` ──> `and` ──> `or`.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Complex threshold evaluation utilizing strict precedence paths
is_authenticated = True
access_level_score = 5

# Without parentheses, 'and' would execute before 'or'
# Evaluation sequence here: (5 > 10) is False -> False and False is False -> True or False is True
calculated_access_result = is_authenticated or access_level_score > 10 and False
print(f"Unparenthesized Execution Result: {calculated_access_result}")

# Forcing alternate logic pathways cleanly utilizing custom explicit groupings
parenthesized_access_result = (is_authenticated or access_level_score > 10) and False
print(f"Parenthesized Overridden Result: {parenthesized_access_result}")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Unparenthesized Execution Result: True
Parenthesized Overridden Result: False
```
</details>

---

## 5. ➕ Membership Operators (in, not in)

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is it?:** Sequence scanner operators engineered to search and validate whether a specific target element pattern exists inside an iterable container array (like a list or tuple).
* **Efficiency:** Provides highly readable, high-speed membership validation loops without writing complex custom search algorithms.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Auditing connection metadata tracks against a targeted whitelist catalog
active_security_whitelist = ["NODE-ALPHA", "NODE-BRAVO", "NODE-CHARLIE"]
incoming_request_node = "NODE-DELTA"

is_node_allowed = incoming_request_node in active_security_whitelist
is_node_blocked = incoming_request_node not in active_security_whitelist

print(f"Access Permission Granted: {is_node_allowed}")
print(f"Firewall Block Mandated: {is_node_blocked}")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Access Permission Granted: False
Firewall Block Mandated: True
```
</details>

---

## 6. ➕ Identity Operators (is, is not)

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is it?:** Memory address comparison checks that verify whether two separate tracking variables point to the exact same tracking location block in physical system RAM.
* **The Crucial Variance Matrix (`==` vs `is`):**
  * `==` (Equality): Audits contents strictly to confirm if the inner data inside the structures matches.
  * `is` (Identity): Ignores the data values and explicitly verifies if the system reference memory IDs (`id()`) are completely identical.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Instantiating separate target dataset lists containing identical structures
memory_pool_alpha = [1024, 2048]
memory_pool_bravo = [1024, 2048]

# Checking structural data equality versus raw memory pointer alignment
are_contents_equal = (memory_pool_alpha == memory_pool_bravo)
are_memory_addresses_identical = (memory_pool_alpha is memory_pool_bravo)

print(f"Data Equality Check (==): {are_contents_equal}")
print(f"Memory Pointer Check (is): {are_memory_addresses_identical}")
print(f"Pool Alpha Memory ID: {id(memory_pool_alpha)} | Pool Bravo Memory ID: {id(memory_pool_bravo)}")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Data Equality Check (==): True
Memory Pointer Check (is): False
Pool Alpha Memory ID: 140412853920256 | Pool Bravo Memory ID: 140412853920832
```
</details>
