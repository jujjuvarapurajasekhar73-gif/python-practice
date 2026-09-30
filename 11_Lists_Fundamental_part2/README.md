---

# 🧺 Module 08: Lists Methods & Analytics (Part 2)

This module covers dynamic list mutation vectors (adding, removing, updating items), dataset validation metrics, and in-place sorting or reversing operations.

---

## 4. 🧺 Modifying Data: Adding, Removing & Updating Items

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

Python provides highly optimized, built-in class methods to mutate list data contents inside memory tracking lanes:
* **Adding Items:**
  * `append(item)` ──> Pushes a single item onto the absolute end of the list.
  * `insert(index, item)` ──> Injects an item at a specific index position, shifting downstream elements to the right.
  * `extend(iterable)` ──> Merges an entire list sequence onto the parent list, flat-unpacking elements.
* **Removing Items:**
  * `pop(index)` ──> Removes and returns the item at the given index. If the index parameter is omitted, it removes the last item.
  * `remove(value)` ──> Searches for and deletes the *first* matching occurrence of a specific value. Throws a `ValueError` if the value is missing.
  * `clear()` ──> Wipes out every single item, leaving the list box completely empty.

```text
Visual Addition Comparison:
Initial List: ["A", "B"]

append(["C", "D"]) ───> ["A", "B", ["C", "D"]] (Nested List added as 1 item)
extend(["C", "D"]) ───> ["A", "B", "C", "D"]    (Merged flat into a single array)
```
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
active_worker_nodes = ["NODE_01", "NODE_02"]

# 1. Dynamic Insertion Mutations (append, insert, extend)
active_worker_nodes.append("NODE_03")
active_worker_nodes.insert(1, "NODE_NEW")
active_worker_nodes.extend(["NODE_04", "NODE_05"])
print("Mutated List after Additions: ", active_worker_nodes)

# 2. Updating items directly using index position assignments
active_worker_nodes[1] = "NODE_UPDATED"
print("Mutated List after Update:    ", active_worker_nodes)

# 3. Dynamic Deletion Mutations (pop, remove)
popped_element_item = active_worker_nodes.pop(1) # Removes "NODE_UPDATED"
active_worker_nodes.remove("NODE_03")            # Wipes out target value match string
print(f"Removed Piece: '{popped_element_item}' | Final Remaining Node Pool: {active_worker_nodes}")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Mutated List after Additions:  ['NODE_01', 'NODE_NEW', 'NODE_02', 'NODE_03', 'NODE_04', 'NODE_05']
Mutated List after Update:    ['NODE_01', 'NODE_UPDATED', 'NODE_02', 'NODE_03', 'NODE_04', 'NODE_05']
Removed Piece: 'NODE_UPDATED' | Final Remaining Node Pool: ['NODE_01', 'NODE_02', 'NODE_04', 'NODE_05']
```
</details>

---

## 5. 🧺 Analyzing Lists & Evaluation Operators (`count()`, `index()`, `in`, `is`)

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **`count(value)`:** Scans the list array linearly from start to finish and returns the total number of times a specific value appears.
* **`index(value)`:** Searches for a specific value and returns its first matching position coordinate index. Throws an error if the item is missing.
* **Membership Verification:** Uses `in` and `not in` operators to verify if an item exists inside a list container, returning `True` or `False`.
* **Identity Verification:** Uses `is` and `is not` to check if two list variables point to the exact same memory box location in RAM, separating content checks from actual address sweeps.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
target_metric_logs = [10, 25, 12, 45, 12, 88]

# 1. Running extraction count and index search sweeps
print(f"Initial Metric List: {target_metric_logs}")
print(f"Count of '12' values inside array: {target_metric_logs.count(12)}")
print(f"Find first position index of '45':   {target_metric_logs.index(45)}")

# 2. Membership checking passes
print("Is 88 present in dataset?:", 88 in target_metric_logs)
print("Is 99 missing from dataset?:", 99 not in target_metric_logs)
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Initial Metric List: [10, 25, 12, 45, 12, 88]
Count of '12' values inside array: 2
Find first position index of '45':   3
Is 88 present in dataset?: True
Is 99 missing from dataset?: True
```
</details>

---

## 6. 🧺 Advanced Data Validation & Sorting (`all()`, `any()`, `sort()`, `reverse()`)

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **Data Aggregation Checkers:**
  * **`all(iterable)`:** Returns `True` **only** if every single element inside the collection evaluates to `True`. If even one item is `False`, it fields a `False` response.
  * **`any(iterable)`:** Returns `True` if **at least one** item inside the container evaluates to `True`. Returns `False` only if the entire list is full of `False` components.
* **Sorting & Ordering Metrics:**
  * **`sort()`:** Alphabetically or numerically sorts the original list directly inline inside memory (**permanently mutates the state**). By default, sorts in ascending order. Pass `reverse=True` to sort in descending order.
  * **`reverse()`:** Flips the order of elements in the list from back to front inline, permanently swapping index mirror tracks.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# 1. Auditing dataset status arrays using all() and any() logic metrics
system_health_checks_pool = [True, True, False, True]
print("Are ALL health metrics green (all)?:", all(system_health_checks_pool))
print("Are ANY health metrics green (any)?:", any(system_health_checks_pool))

# 2. In-place sorting and reversing modifications
target_sensor_data = [99, 12, 45, 7, 88]

target_sensor_data.sort() # Sorting elements permanently in ascending order
print("\nSorted Sensor Array In-Place:   ", target_sensor_data)

target_sensor_data.reverse() # Inverting sequence permanently into descending layout
print("Reversed Sensor Array In-Place: ", target_sensor_data)
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Are ALL health metrics green (all)?: False
Are ANY health metrics green (any)?: True

Sorted Sensor Array In-Place:    [7, 12, 45, 88, 99]
Reversed Sensor Array In-Place:  [99, 88, 45, 12, 7]
```
</details>
