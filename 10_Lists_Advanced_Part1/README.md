# 🗂️ Module 10: Data Structures - Lists Advanced (Part 1)

This module explores deeper memory management concepts within Python sequences, focusing on shallow versus deep duplication anomalies, structural container merging, iterator stream traversal state layers, and high-performance functional data transformations.

---

## 1. 🗂️ Copying Lists: Shallow Copy vs Deep Copy

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is it?:** Methodologies used to duplicate data arrays so you can safely alter values without corrupting the original master data setup inside memory databases.
* **The Structural Variance Matrix:**
  * **Shallow Copy (`.copy()`):** Creates a brand-new top-level parent container array, but if there are nested inner sub-lists inside, it merely copies their reference pointers. Modifying a nested item will impact *both* the original and duplicated lists.
  * **Deep Copy (`copy.deepcopy()`):** Recursively allocates fully separated, standalone memory reference addresses for all sub-levels and inner nested elements. This ensures complete structural isolation between the two containers.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
import copy

# Simulating a nested network node configuration profile
original_profile = [["US-EAST", "ACTIVE"], "NODE-01"]

# 1. Executing a standard Shallow Copy mutation path
shallow_mirror = original_profile.copy()

# 2. Executing a strict standalone Deep Copy transaction layer
deep_isolated = copy.deepcopy(original_profile)

# Modifying the inner nested reference element block to trace structural behavior differences
original_profile[0][1] = "TERMINATED"

print(f"Original Profile Base Array: {original_profile}")
print(f"Shallow Copy Mirror Impact:   {shallow_mirror}")   # Impacted by nested alteration
print(f"Deep Copy Protected Layer:    {deep_isolated}")   # Completely safe from corruption
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Original Profile Base Array: [['US-EAST', 'TERMINATED'], 'NODE-01']
Shallow Copy Mirror Impact:   [['US-EAST', 'TERMINATED'], 'NODE-01']
Deep Copy Protected Layer:    [['US-EAST', 'ACTIVE'], 'NODE-01']
```
</details>

---

## 2. 🗂️ Combining Lists & Zip Function

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is it?:** The built-in `zip(*iterables)` function takes multiple parallel lists and stitches them together coordinate-by-coordinate into an iterable pool of combined tuple elements.
* **The Truncation Protocol Notice:** If the source lists vary in length, the `zip()` function automatically stops processing as soon as the shortest container runs out of elements, discarding any leftover items from the longer list.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Merging separate metrics collections into paired runtime configurations
monitored_nodes = ["NODE-ALPHA", "NODE-BRAVO", "NODE-CHARLIE"]
recorded_cpu_loads = [42, 88, 14]

# Combining data arrays into an active tuple list matrix via zip
aggregated_telemetry_map = list(zip(monitored_nodes, recorded_cpu_loads))

print(f"Aggregated Telemetry Map: {aggregated_telemetry_map}")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Aggregated Telemetry Map: [('NODE-ALPHA', 42), ('NODE-BRAVO', 88), ('NODE-CHARLIE', 14)]
```
</details>

---

## 3. 🗂️ Iterables & Iterators

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **The Core Structural Divergence Matrix:**
  * **Iterable:** Any foundational object container (like a List, String, or Tuple) capable of exposing its elements sequentially when processed. It has an internal `__iter__` method block.
  * **Iterator:** The explicit state-tracking traversal pointer engine built by passing an iterable to the `iter()` function. It manually steps through the data sequence one entry at a time utilizing the `next()` function, keeping track of its current position.
* **Completion Indicator:** When an iterator runs out of elements, invoking `next()` throws a native `StopIteration` flag to signal that the data stream is exhausted.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Manual sequential text array streaming using iterator mechanics
raw_inventory_stack = ["Asset_A", "Asset_B"]

# Extracting the active tracking iterator object stream state wrapper
stack_stream_iterator = iter(raw_inventory_stack)

print(f"First Traversal Entry Fetch:  {next(stack_stream_iterator)}")
print(f"Second Traversal Entry Fetch: {next(stack_stream_iterator)}")

# Calling next() once more would throw a native StopIteration flag exception
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
First Traversal Entry Fetch:  Asset_A
Second Traversal Entry Fetch: Asset_B
```
</details>

---

## 4. 🗂️ Map Function (Functional Data Transformation)

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is it?:** The built-in `map(function, iterable)` function passes every single item from a data collection through a specific processing function, returning an optimized iterator of the newly transformed values.
* **Production Context:** Extremely performant for mass cleansing, parsing, or standardizing raw fields without relying on verbose, slower manual `for` loop iteration tracks.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# A simple transformation helper rule to standardize node names
def convert_to_uppercase_log(raw_word):
    return f"LOG_{raw_word.upper()}"

raw_environment_tags = ["staging", "production", "testing"]

# Running mass data scaling transformations using map loops
transformed_tags_stream = map(convert_to_uppercase_log, raw_environment_tags)

# Casting the resulting iterator back into a readable list format block
sanitized_tags_index = list(transformed_tags_stream)
print(f"Transformed Registry Model: {sanitized_tags_index}")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Transformed Registry Model: ['LOG_STAGING', 'LOG_PRODUCTION', 'LOG_TESTING']
```
</details>

---

## 5. 🗂️ Filter Function (Functional Data Auditing)

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is it?:** The built-in `filter(boolean_function, iterable)` function checks every entry in a collection against a specific validation rule, dropping items that fail the test and returning an optimized iterator of the passing elements.
* **Mechanism:** The evaluation function must return a strict boolean state (`True` or `False`). Items that resolve to False are instantly stripped from the outgoing data stream pipeline.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# A simple validation helper rule to isolate high-risk latency metrics
def is_latency_critical(latency_value):
    return latency_value > 5.0

live_network_latencies = [1.25, 12.40, 3.12, 8.95, 0.45]

# Filtering out low-priority metrics using functional audit sweeps
critical_incidents_stream = filter(is_latency_critical, live_network_latencies)

# Casting the resulting filtered iterator into a readable list structure
extracted_anomalies_register = list(critical_incidents_stream)
print(f"Isolated Critical Latency Anomalies: {extracted_anomalies_register}")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Isolated Critical Latency Anomalies: [12.4, 8.95]
```
</details>
