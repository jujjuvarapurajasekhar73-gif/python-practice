# 🗂️ Module 10: Advanced Data Structures Mastery

This module covers Python's core collection containers, including immutable sequence models (Tuples), unique element hash grids (Sets), and associative key-value schema pools (Dictionaries).

---

## 1. 🗂️ Tuples (Immutable Value Sequences)

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is a Tuple?:** A tuple is an ordered collection of items wrapped inside parentheses `()`. It works exactly like a list, with one absolute structural difference: **Tuples are strictly immutable**.
* **The Immutability Law:** Once a tuple is created in memory, its values cannot be added, removed, modified, or updated. If you try to reassign an index slot, Python immediately throws a `TypeError` crash.
* **Why Use It?:** Protects system-critical constants (like coordinate records, fixed configuration settings, or database connection keys) from accidental edits downstream.

```text
Visual Memory Blueprint:
my_tuple = ( 73, "PRD" )  ───> [ Locked Memory Grid ] ───> Attempt to change ───> [ TypeError Crash ]
```
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Instantiating immutable tuple constant configuration layouts
geo_coordinates_record = (17.4482, 78.5375)
print(f"Target Geolocation Tuple: {geo_coordinates_record} | Type: {type(geo_coordinates_record)}")

# Standard indexing access operations work perfectly
print("Extracting Latitude Coordinate (Index 0):", geo_coordinates_record[0])

# Note: Writing geo_coordinates_record[0] = 19.99 will trigger an immediate system crash
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Target Geolocation Tuple: (17.4482, 78.5375) | Type: <class 'tuple'>
Extracting Latitude Coordinate (Index 0): 17.4482
```
</details>

---

## 2. 🗂️ Sets: Unique Element Arrays & Math Operations

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is a Set?:** An unordered collection of unique elements wrapped inside curly braces `{}`. Sets **never** store duplicate values; if you append duplicate items, they are automatically dropped.
* **Core Characteristics:** Elements are unindexed. You cannot fetch values using index coordinates (like `set[0]`).
* **Relational Math Operations Matrix:**
  * `union()` (`|`) ──> Merges elements from both sets together, dropping duplicates.
  * `intersection()` (`&`) ──> Isolates and keeps **only** the matching elements present in both sets.
  * `difference()` (`-`) ──> Keeps elements found in the first set but missing from the second set.

```text
📊 Venn Diagram Logic Representation:
Set A: { 10, 20 }
Set B: { 20, 30 }
Intersection (A & B) ───> Isolates matching token: { 20 }
```
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# 1. Automatic duplicate removal validation pass
raw_incoming_logs = {"IP_A", "IP_B", "IP_A", "IP_C"}
print("Sanitized Unique Ingestion Set Pool: ", raw_incoming_logs)

# 2. Executing relational set math sweeps
active_cluster_alpha = {"Node_1", "Node_2", "Node_3"}
active_cluster_bravo = {"Node_3", "Node_4", "Node_5"}

print("Union (All Unique Nodes):    ", active_cluster_alpha | active_cluster_bravo)
print("Intersection (Shared Nodes): ", active_cluster_alpha & active_cluster_bravo)
print("Difference (Alpha - Bravo):  ", active_cluster_alpha - active_cluster_bravo)
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Sanitized Unique Ingestion Set Pool:  {'IP_B', 'IP_C', 'IP_A'}
Union (All Unique Nodes):     {'Node_3', 'Node_2', 'Node_1', 'Node_5', 'Node_4'}
Intersection (Shared Nodes):  {'Node_3'}
Difference (Alpha - Bravo):   {'Node_2', 'Node_1'}
```
</details>

---

## 3. 🗂️ Dictionaries Foundations (Key-Value Schema Maps)

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is a Dictionary?:** An unordered collection of key-value pairs enclosed in curly braces `{}`. Data is retrieved using unique identifier keys instead of index numbers.
* **Core Rules Checklist:** Keys must be completely unique and immutable (like strings or integers). Values can be anything (lists, booleans, nested dictionaries) and can change freely.
* **Production Advantage:** Provides instant data lookups matching specific identifiers perfectly, making it the standard format for JSON data streams and API profiles.

```text
Visual Key-Value Storage Schema Map:
Name:   "user_73"  ───> Maps to Data Box ───> { "role": "admin", "clearance": 3 }
```
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Instantiating a structured schema metadata dictionary profile mapping
production_node_profile = {
    "node_id": "PRD_NODE_73",
    "load_metric": 45.2,
    "is_active": True
}

print(f"Dictionary Object Content: {production_node_profile} -> Type: {type(production_node_profile)}")

# Accessing internal data variables utilizing identifier primary keys explicitly
print("Fetching Localized Load Factor Value:", production_node_profile["load_metric"])
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Dictionary Object Content: {'node_id': 'PRD_NODE_73', 'load_metric': 45.2, 'is_active': True} -> Type: <class 'dict'>
Fetching Localized Load Factor Value: 45.2
```
</details>

---

## 4. 🗂️ Dictionary Methods & Safe Data Extraction

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

Python provides specialized methods to read and modify dictionaries safely without causing program crashes:
* **`get(key, default)`:** Fetches a value matching a specific key. If the key is missing from the dictionary, it safely returns a predefined fallback default message instead of crashing your program.
* **`keys()`:** Extracts an array index containing **only** the identifier keys.
* **`values()`:** Extracts an array index containing **only** the data value sets.
* **`items()`:** Unpacks the entire dictionary into a collection of `(key, value)` tuples, which is ideal for step-by-step looping scans.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
client_ledger_profile = {"account_name": "Raja Shekar", "balance": 50000.0}

# 1. Safe data extraction utilizing the get() safeguard gate fallback method
print("Safe extraction check (Key exists):  ", client_ledger_profile.get("balance"))
print("Safe extraction check (Key missing): ", client_ledger_profile.get("missing_key", "FALLBACK_O_DATA"))

# 2. Extracting specific object arrays
print("\nExtracted Dictionary Keys Structure:  ", list(client_ledger_profile.keys()))
print("Extracted Dictionary Values Structure:", list(client_ledger_profile.values()))

# 3. Traversal tracking iterations utilizing items() loops
print("\nInitiating Dictionary Items Loop Sweep:")
for access_key, data_value in client_ledger_profile.items():
    print(f" -> Mapping Node Identifier: '{access_key}' maps to Data Cell: {data_value}")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Safe extraction check (Key exists):   50000.0
Safe extraction check (Key missing):  FALLBACK_O_DATA

Extracted Dictionary Keys Structure:   ['account_name', 'balance']
Extracted Dictionary Values Structure: ['Raja Shekar', 50000.0]

Initiating Dictionary Items Loop Sweep:
 -> Mapping Node Identifier: 'account_name' maps to Data Cell: Raja Shekar
 -> Mapping Node Identifier: 'balance' maps to Data Cell: 50000.0
```
</details>
