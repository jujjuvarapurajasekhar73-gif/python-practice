# 🔁 Module 7: Control Flow - While Loops

This module covers conditional-driven loop persistence, infinite monitoring structures via `While True`, structural resource differences between conditional and incremental loops, and practical validation challenge execution models.

---

## 1. 🔁 While Loop & While Condition

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is it?:** An indefinite control flow architecture that repeatedly runs a specific block of statements as long as its core conditional expression remains `True`.
* **The Modifier Constraint:** Always guarantee that the variable properties driving the evaluation condition are explicitly modified programmatically inside the loop body, causing it to eventually resolve to `False` to prevent severe system hardware locks.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Processing a backlog queue of infrastructure data packets sequentially
remaining_queue_jobs = 3

while remaining_queue_jobs > 0:
    print(f"[QUEUE_ENG] Processing job token ticket. Active Backlog Pool: {remaining_queue_jobs}")
    # Explicitly modifying the condition variable property to prevent freeze cycles
    remaining_queue_jobs -= 1

print("[QUEUE_ENG] Job backlog pipeline fully cleared.")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
[QUEUE_ENG] Processing job token ticket. Active Backlog Pool: 3
[QUEUE_ENG] Processing job token ticket. Active Backlog Pool: 2
[QUEUE_ENG] Processing job token ticket. Active Backlog Pool: 1
[QUEUE_ENG] Job backlog pipeline fully cleared.
```
</details>

---

## 2. 🔁 While True Loops

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is it?:** An intentional infinite looping design framework utilizing a static logical state wrapper of `While True`. 
* **Mechanism:** The loop processes code lines continuously without checking boundaries at the top. The loop relies entirely on internal runtime conditional checkpoints calling a clean `break` command statement to exit the block safely.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Simulating a persistent application event listener loop tracking inbound network hits
polling_cycle_ticker = 0

while True:
    polling_cycle_tracker = polling_cycle_ticker + 1
    print(f"[LISTENER] Listening on live stream channel endpoints... Heartbeat Node: {polling_cycle_tracker}")
    
    # Internal conditional exit trigger checkpoint
    if polling_cycle_tracker >= 2:
        print("[LISTENER] Safe session threshold reached. Terminating connection safely.")
        break  # Kills the infinite loop run immediately
        
    polling_cycle_tracker += 1
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
[LISTENER] Listening on live stream channel endpoints... Heartbeat Node: 1
[LISTENER] Listening on live stream channel endpoints... Heartbeat Node: 2
[LISTENER] Safe session threshold reached. Terminating connection safely.
```
</details>

---

## 3. 🔁 While Condition vs While True

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **The Core Structural Variance Matrix:**
  * **While Condition:** The engine performs a strict threshold validation check at the very top header boundary of *every single cycle* before running any code lines below it.
  * **While True:** Bypasses top header checks completely, forcing immediate processing pass entry. The loop relies entirely on middle or lower logic checkpoints calling a `break` command to stop execution loops.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Standard Validation Loop Check (Top Boundary Bounded)
limit_check = 0
while limit_check < 0:
    print("This statement will never print because the boundary check immediately fails.")

# Infinite Entry Loop Check with Middle Branch Bounded Control
while True:
    print("[EXECUTION] Executed first pass line before hitting internal boundary check.")
    break
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
[EXECUTION] Executed first pass line before hitting internal boundary check.
```
</details>

---

## 4. 🔁 While vs For Loops (Structural Resource Allocation)

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **The Selection Standards Matrix:**
  * **`for` Loop:** Deployed when the absolute dimensions of a collection index array or repetition cycle count are known beforehand (Definite Iteration).
  * **`while` Loop:** Deployed when loop continuation depends strictly on dynamic logical evaluation triggers, where the final processing lifetime duration is unpredictable at startup (Indefinite Iteration).
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Fixed-Dimension Sequence Processing (Optimal for 'for' loops)
pre_calculated_nodes = ["NODE_A", "NODE_B"]
for node in pre_calculated_nodes:
    print(f"[FOR_LOOP] Target Processed: {node}")

# Dynamic Event-Driven Processing (Optimal for 'while' loops)
system_buffer_space = 100
while system_buffer_space > 40:
    print(f"[WHILE_LOOP] Cleaning system buffer capacity core. Active Space: {system_buffer_space}%")
    system_buffer_space -= 35  # Reduces space down iteratively until logic breaks
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
[FOR_LOOP] Target Processed: NODE_A
[FOR_LOOP] Target Processed: NODE_B
[WHILE_LOOP] Cleaning system buffer capacity core. Active Space: 100%
[WHILE_LOOP] Cleaning system buffer capacity core. Active Space: 65%
```
</details>

---

## 5. 🔁 Python Challenge (Loop Mastery Exercise)

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **The Optimization Challenge:** Building a clean string processing parser utilizing dynamic `while` conditions to securely unpack telemetry input frames, removing layout whitespace defects and validating characters inline.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Processing dynamic inbound token strings character-by-character via custom while indices
raw_payload_stream = "X9B2_PROD"
stream_processing_index = 0
total_stream_length = len(raw_payload_stream)

print(f"--- Initiating Inbound Stream Scan (Length: {total_stream_length}) ---")

while stream_processing_index < total_stream_length:
    individual_char_node = raw_payload_stream[stream_processing_index]
    
    # Executing localized validation logic transformations inline
    if individual_char_node.isdigit():
        print(f"   [PARSER_ALERT] Numeric Digit Node Traced at Position {stream_processing_index}: '{individual_char_node}'")
    else:
        print(f"   [PARSER_LOG] Alphabetic Character Node Tracked: '{individual_char_node}'")
        
    stream_processing_index += 1  # Standard increment step logic routing
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
--- Initiating Inbound Stream Scan (Length: 9) ---
   [PARSER_LOG] Alphabetic Character Node Tracked: 'X'
   [PARSER_ALERT] Numeric Digit Node Traced at Position 1: '9'
   [PARSER_LOG] Alphabetic Character Node Tracked: 'B'
   [PARSER_ALERT] Numeric Digit Node Traced at Position 3: '2'
   [PARSER_LOG] Alphabetic Character Node Tracked: '_'
   [PARSER_LOG] Alphabetic Character Node Tracked: 'P'
   [PARSER_LOG] Alphabetic Character Node Tracked: 'R'
   [PARSER_LOG] Alphabetic Character Node Tracked: 'O'
   [PARSER_LOG] Alphabetic Character Node Tracked: 'D'
```
</details>
