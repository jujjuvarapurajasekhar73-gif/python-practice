# 🎛️ Module 06: Conditional Statements

This module covers Python's dynamic conditional branching systems, structure blocks isolation rules using indentation, compound logic gateways, ternary short-circuits, and pattern-matching layouts.

---

## 1. 🎛️ Conditional Statement 'if' & Indentation Rules

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is a Conditional Statement?:** Conditional statements check conditions and change how the program behaves based on the result. They allow code to make dynamic decisions at runtime.
* **The Indentation Law:** Unlike other programming languages that use curly braces `{}`, Python relies strictly on whitespaces (spaces or tabs) to group statements together into a single block of code. 
* **Critical Guideline:** An incorrect indentation level immediately breaks the script layout execution structure and triggers an unexpected `IndentationError` crash pass.

```text
Visual Code Block Mapping:
if condition == True:
└───> [ Statement Row 1 ]  <─── (Indented by exactly 4 spaces)
└───> [ Statement Row 2 ]  <─── (Belongs to the same execution block)
[ Main Statement Row 3 ]   <─── (Outdent: Runs independently outside the if block)
```
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Evaluating system parameter matrices using a baseline if block logic boundary
active_cpu_overhead = 88

if active_cpu_overhead > 80:
    print("[ALERT] Target metric breaches designated safe parameter zone limits!")
    print("[ALERT] Initializing dynamic cooling distribution frameworks...")

print("System heartbeat check completed successfully.")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
[ALERT] Target metric breaches designated safe parameter zone limits!
[ALERT] Initializing dynamic cooling distribution frameworks...
System heartbeat check completed successfully.
```
</details>

---

## 2. 🎛️ Dual & Multi-Branch Logic (if, elif, else)

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **`else` Block:** Acts as an automated catch-all branch fallback path. It executes its internal block statements strictly if the preceding `if` condition resolves to `False`.
* **`elif` (Else-If) Chain:** Used when your business logic requires checking multiple distinct conditions sequentially. Python sweeps down the chain one-by-one; the moment it finds a condition that evaluates to `True`, it runs that specific block and short-circuits (skips) the rest of the file layout.

```text
📊 Execution Flow Pipeline:
 [ Input Value ] ───> Is if True? ───YES───> [ Run Block A ] ───> Exit Chain
                          │
                        FALSE
                          │
                    Is elif True? ───YES───> [ Run Block B ] ───> Exit Chain
                          │
                        FALSE
                          │
                          ▼
                  [ Run else Block ] ───> Exit Chain
```
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Categorizing system telemetry values using a clean structural multi-tier chain layout
current_system_load = 45

if current_system_load >= 80:
    system_tier_rating = "CRITICAL_OVERHEAD"
elif current_system_load >= 50:
    system_tier_rating = "WARNING_OVERHEAD"
else:
    system_tier_rating = "OPTIMAL_LOAD_BALANCED"

print(f"Computed System Registry Performance Rating: {system_tier_rating}")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Computed System Registry Performance Rating: OPTIMAL_LOAD_BALANCED
```
</details>

---

## 3. 🎛️ Nested if Structural Blocks

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is it?:** Placing a conditional check block completely inside the inner statement layout rows of another parent conditional block.
* **Operational Rule:** The inner nested conditions are completely unreachable unless the primary parent condition evaluates to `True` first. Use nested statements carefully; deep nesting layers can rapidly reduce code readability.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Conducting a multi-layer deep security screening check loop
has_valid_access_key = True
is_security_clearance_level_3 = False

if has_valid_access_key:
    print("[SECURITY] Parent authentication token validation passed.")
    
    # Nested child logic checkpoint layer
    if is_security_clearance_level_3:
        print("[SECURITY] Core mainframe root database access granted.")
    else:
        print("[SECURITY] Operational Halt: Insufficient localized permission tiers.")
else:
    print("[SECURITY] Access Rejected: Target signature mismatched.")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
[SECURITY] Parent authentication token validation passed.
[SECURITY] Operational Halt: Insufficient localized permission tiers.
```
</details>

---

## 4. 🎛️ Conditions with Logical Operators vs Independent if Blocks

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **Independent `if` Blocks:** Every single standalone `if` block is checked sequentially, regardless of whether previous conditions passed or failed.
* **Compound Conditions with Logical Operators (`and` / `or`):** Combines multiple logic checkpoints into a single elegant statement row. This approach eliminates messy nested blocks, keeps indentation shallow, and makes the code clean and professional.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Standardizing clean compound evaluations over complex nested structures
is_network_stable = True
is_replica_node_synced = True

# Combining checks cleanly using an explicit logical 'and' gate connector
if is_network_stable and is_replica_node_synced:
    print("[PIPELINE] Data migration sync operation triggered smoothly.")
else:
    print("[PIPELINE] Data migration sync halted. Infrastructure anomalies caught.")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
[PIPELINE] Data migration sync operation triggered smoothly.
```
</details>

---

## 5. 🎛️ Inline if (Ternary Operator Expression)

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is it?:** A compact, single-line shorthand syntax used to assign values to variables based on a condition check.
* **Syntax Blueprint Rule:** `value_if_true if condition else value_if_false`
* **Enterprise Benefit:** Dramatically minimizes code boilerplate when writing simple variable choices, keeping your architecture files concise and highly scannable.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Utilizing compact inline ternary structures to assign system state values
node_ping_latency_ms = 12

# Evaluating structural metrics inline in a single statement row
network_tier_status = "CRITICAL_LAG" if node_ping_latency_ms > 100 else "OPTIMAL_FAST"

print(f"Target Cluster Latency Evaluation Outcome: {network_tier_status}")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Target Cluster Latency Evaluation Outcome: OPTIMAL_FAST
```
</details>

---

## 6. 🎛️ Modern Structural Pattern Matching (match case)

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is it?:** Introduced in modern Python environments, the `match case` pattern-matching framework provides a highly optimized, readable structural alternative to long, repetitive `if-elif-else` chains.
* **The `_` Fallback Token:** The underscore character token `case _:` operates as the absolute final catch-all branch. It acts exactly like the standard `else` block to process unmapped values safely.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Simulating an inbound API routing endpoint engine using match-case blocks
inbound_api_response_code = 404

match inbound_api_response_code:
    case 200:
        operation_diagnostic_msg = "SUCCESSFUL_TRANSACTION_PAYLOAD"
    case 404:
        operation_diagnostic_msg = "RESOURCE_NOT_FOUND_EXCEPTION"
    case 500:
        operation_diagnostic_msg = "INTERNAL_SERVER_CRASH_ANOMALY"
    case _:
        operation_diagnostic_msg = "UNKNOWN_NETWORK_STATUS_CODE"

print(f"Routing Matrix Ingest Trace Outcome: {operation_diagnostic_msg}")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Routing Matrix Ingest Trace Outcome: RESOURCE_NOT_FOUND_EXCEPTION
```
</details>
