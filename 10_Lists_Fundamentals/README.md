# 🧺 Module 08: Lists Fundamentals (Part 1)

This module covers Python's linear mutable array containers, multi-dimensional nested matrices, and dynamic data structural sequence unpacking mechanics.

---

## 1. 🧺 Data Structures & Creating Lists

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is a Data Structure?:** A specialized format tool used to organize, manage, and store multiple grouped data values inside computer memory efficiently.
* **The `list` Container:** A built-in data structure that holds an ordered, changeable (mutable) collection of items wrapped inside square brackets `[]`.
* **Core Characteristics:**
  * **Ordered:** Items maintain their exact insertion position sequences.
  * **Mutable:** You can add, modify, or delete elements directly inside the list without creating a new list box.
  * **Heterogeneous:** A single list box can store mixed data types simultaneously (strings, integers, floats, booleans).

```text
Visual Memory Box Allocation:
my_list = [ 10, "Production", True ]
           ├───> Index 0: Integer Data Type Slot (int)
           ├───> Index 1: String Text Data Type Slot (str)
           └───> Index 2: Logical Boolean Data Type Slot (bool)
```
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Instantiating multi-value data structure lists
empty_registry_pool = []
active_cluster_nodes = ["NODE-01", "NODE-02", "NODE-03"]
mixed_telemetry_dataset = [73, "OPTIMAL", 98.6, True]

print(f"Cluster Inventory Content: {active_cluster_nodes} -> Type: {type(active_cluster_nodes)}")
print(f"Mixed Dataset Content:     {mixed_telemetry_dataset} -> Type: {type(mixed_telemetry_dataset)}")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Cluster Inventory Content: ['NODE-01', 'NODE-02', 'NODE-03'] -> Type: <class 'list'>
Mixed Dataset Content:     [73, 'OPTIMAL', 98.6, True] -> Type: <class 'list'>
```
</details>

---

## 2. 🧺 Indexing, Slicing & Multi-Dimensional Nested Lists

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **Indexing & Slicing:** Works exactly like string character arrays. Positive coordinates start at `0` from the left, while negative coordinates start at `-1` from the right. Slicing extracts sub-lists using the standard layout formula: `list[start:end:step]` (where the end position is excluded).
* **Nested Lists (Multi-Dimensional Arrays):** Placing a list structure inside another parent list container box. Used to map data grids, data sheets, or coordinates matrices.

```text
🧠 Nested List Index Matrix Map:
matrix_grid = [[1, 2], [3, 4]]
                ├───> Index 0 points to child array [1, 2]
                └───> Index 1 points to child array [3, 4]

To target value 4: matrix_grid[1][1] ───> Row Index 1, Column Index 1
```
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
target_hardware_inventory = ["Server", "Router", "Switch", "Firewall", "Gateway"]

# 1. Standard Indexing and Slicing sweeps
print("Primary Element Fetch (Index 0):  ", target_hardware_inventory[0])
print("Terminal Element Fetch (Index -1): ", target_hardware_inventory[-1])
print("Slicing Subset Window (Index 1:4):", target_hardware_inventory[1:4])

# 2. Managing Multi-Dimensional Nested Data Matrix Structures
multi_dimensional_cluster_matrix = [["CPU_01", "LOAD_22"], ["CPU_02", "LOAD_85"]]
print("\nTargeting Nested Array Row 1 Block:", multi_dimensional_cluster_matrix[1])
print("Extracting Specific Nested Load Value Cells:", multi_dimensional_cluster_matrix[1][1])
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Primary Element Fetch (Index 0):   Server
Terminal Element Fetch (Index -1): Gateway
Slicing Subset Window (Index 1:4): ['Router', 'Switch', 'Firewall']

Targeting Nested Array Row 1 Block: ['CPU_02', 'LOAD_85']
Extracting Specific Nested Load Value Cells: LOAD_85
```
</details>

---

## 3. 🧺 Advanced Data Unpacking (Asterisk `*` & Underscore `_`)

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **Standard Unpacking:** Unpacks elements from a list directly into individual standalone variable boxes. The number of variables must match the list length perfectly, or Python throws an error.
* **Asterisk `*` Operator (Extended Unpacking):** Gathers multiple leftover elements into a single list variable. Extremely useful when extracting a few target items while grouping the remaining values together.
* **Underscore `_` Placeholder:** Acts as a dummy variable. Use it to catch and completely discard unwanted elements during unpacking passes, keeping your code clean.

```text
Visual Unpacking Model:
[ Item1, Item2, Item3 ] ───> target_a, *leftover = [ Item1, Item2, Item3 ]
                              ├───> target_a = Item1
                              └───> leftover = [ Item2, Item3 ]
```
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
system_log_packet_row = ["2026-SEP-30", "LOG_WARN", "API_TIMEOUT", "SUITE_ALPHA", "NODE_73"]

# 1. Standard absolute unpacking array pass
log_date, log_severity, log_message, _, _ = system_log_packet_row
print(f"Standard Unpack Capture -> Severity: {log_severity} | Message: {log_message}")

# 2. Advanced extended unpacking utilizing Asterisk (*) and Underscore (_) variables
event_date, event_tier, *environment_metadata_tags = system_log_packet_row
print(f"Extended Unpack Capture -> Date: {event_date} | Tier: {event_tier}")
print(f"Grouped Leftover Metadata Tags Array Stack: {environment_metadata_tags}")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Standard Unpack Capture -> Severity: LOG_WARN | Message: API_TIMEOUT
Extended Unpack Capture -> Date: 2026-SEP-30 | Tier: LOG_WARN
Grouped Leftover Metadata Tags Array Stack: ['API_TIMEOUT', 'SUITE_ALPHA', 'NODE_73']
```
</details>
