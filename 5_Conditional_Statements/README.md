# 🔠 Module 5: Conditional Statements

This module covers binary decision structures, blocks indentation compliance, complex multi-branch routing, inline short-hands, and advanced structural pattern matching in Python.

---

## 1. 🔠 Conditional Statement `if` & Indentation Rules

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is it?:** The baseline conditional structure that runs a specific block of statements only if a chosen criteria evaluates to `True`.
* **Indentation Mechanics:** Python doesn't use curly braces `{}` to identify block nesting parameters. It relies strictly on uniform whitespace indentation (PEP 8 standardizes this at **4 spaces**). Missing or uneven spacing instantly crashes your program with an `IndentationError`.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Verifying infrastructure resource capacity limits
active_server_cpu_load = 65

if active_server_cpu_load < 80:
    # This block executes strictly because the expression is True
    print("[SYSTEM_MONITOR] CPU load levels are safe.")
    print("[SYSTEM_MONITOR] Allocation routine pass complete.")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
[SYSTEM_MONITOR] CPU load levels are safe.
[SYSTEM_MONITOR] Allocation routine pass complete.
```
</details>

---

## 2. 🔠 Else & Elif Control Pathways

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is it?:** Multi-branch conditional routing structures used to handle multiple alternate execution paths.
* **Mechanism:**
  * `elif` (Else If): Evaluates a new condition chain only if all preceding options fail.
  * `else`: Acts as a terminal fallback security net catch, executing strictly if no prior conditions resolve as true.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Automated response engine for microservice network routing statuses
target_http_status = 404

if target_http_status == 200:
    print("[ROUTING] Connection verified. Dispatching data packets.")
elif target_http_status == 404:
    print("[ROUTING_WARN] Endpoint not traced. Target resource missing.")
elif target_http_status == 500:
    print("[ROUTING_ERR] Remote hardware crash identified. Switching node pathways.")
else:
    print("[ROUTING_ERR] General runtime exception matched.")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
[ROUTING_WARN] Endpoint not traced. Target resource missing.
```
</details>

---

## 3. 🔠 Nested `if` Structure

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is it?:** A multi-layered control configuration where an inner conditional path block statement resides entirely inside the body perimeter of an existing parent `if` clause.
* **Execution:** The runtime engine sweeps the interior checkpoint line *only* if the top parent constraint passes successfully.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Evaluating system access configurations via a multi-tier checkpoint gateway
is_client_authenticated = True
has_admin_permissions = False

if is_client_authenticated:
    print("[GATEWAY] Session verified. Auditing resource credentials...")
    if has_admin_permissions:
        print("[GATEWAY_SUCCESS] Full root configuration dashboard unlocked.")
    else:
        print("[GATEWAY_REJECT] Inbound request dropped due to missing admin permissions.")
else:
    print("[GATEWAY_REJECT] User tracking session is unauthenticated.")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
[GATEWAY] Session verified. Auditing resource credentials...
[GATEWAY_REJECT] Inbound request dropped due to missing admin permissions.
```
</details>

---

## 4. 🔠 Conditions and Logical Operators

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is it?:** Merging multiple distinct logical constraints inside a single `if` statement line utilizing condition gates (`and`, `or`, `not`).
* **Clean Code Alternative Tip:** Always prefer combining simple nested conditions with unified logical operators to flatten deep indentation nesting blocks.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Evaluating complex compliance thresholds using clean condition gating parameters
is_node_active = True
available_memory_gb = 32

# Flat evaluation path bypassing complex nested nesting blocks
if is_node_active and available_memory_gb >= 16:
    print("[ORCHESTRATOR] Node approved for enterprise computing workloads.")
else:
    print("[ORCHESTRATOR] Target node fails performance validation criteria.")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
[ORCHESTRATOR] Node approved for enterprise computing workloads.
```
</details>

---

## 5. 🔠 Independent `if` Blocks

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is it?:** A sequence of individual, unlinked conditional blocks where every separate `if` block statement is audited sequentially by the runtime engine, regardless of prior outcomes.
* **Contrast:** Unlike an `if-elif` chain (where a single true match skips the rest), independent `if` statements allow multiple blocks to execute simultaneously if their conditions match.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Triggering parallel incident warning trackers for independent components
system_latency_ms = 120
disk_storage_utilization = 95

if system_latency_ms > 100:
    print("[ALERT] Target response latency limits breached.")

if disk_storage_utilization > 90:
    print("[ALERT] High local storage overhead identified on node disk.")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
[ALERT] Target response latency limits breached.
[ALERT] High local storage overhead identified on node disk.
```
</details>

---

## 6. 🔠 Inline `if` (Ternary Operator)

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is it?:** A highly compact, single-line shorthand notation used to evaluate expression parameters and return an assignment target based on a boolean outcome.
* **Syntax Structure:** `true_value if condition else false_value`.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Standardizing server classifications efficiently using inline syntax
connection_pool_requests = 45

# Executing inline condition assignment evaluation checks
node_safety_status = "CRITICAL" if connection_pool_requests > 30 else "OPTIMAL"
print(f"System Threat Assessment Status: {node_safety_status}")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
System Threat Assessment Status: CRITICAL
```
</details>

---

## 7. 🔠 Match Case (Structural Pattern Matching)

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is it?:** Introduced in Python 3.10, `match-case` blocks provide optimized structural pattern matching architectures, functioning as a clean, performant replacement for massive nested `if-elif` trees.
* **The Default Match Wrapper:** The underscore character (`_`) acts as a wildcard catch-all parameter, executing cleanly if no explicit case blocks match the target data input token.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Processing dynamic server command signals through match-case pattern evaluations
system_event_directive = "TERMINATE_NODE"

match system_event_directive:
    case "START_NODE":
        print("[CORE_ENGINE] Activating remote clustering pipeline allocation loops.")
    case "REBOOT_NODE":
        print("[CORE_ENGINE] Triggering graceful sub-system restart cycles.")
    case "TERMINATE_NODE":
        print("[CORE_ENGINE] Hard infrastructure deployment shutdown sequence committed.")
    case _:
        print("[CORE_ENGINE] Unknown system signature command token matched.")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
[CORE_ENGINE] Hard infrastructure deployment shutdown sequence committed.
```
</details>
