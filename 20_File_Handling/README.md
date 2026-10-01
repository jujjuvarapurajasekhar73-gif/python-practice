# 📂 Module 20: File Handling

This module covers Python's persistent external storage communication layers, stream ingestion modes (Read, Write, Append), resource leakage safety walls (Context Managers), and sequential row parsing architectures.

---

## 1. 📂 File Streams & Resource Persistence Foundations

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is File Handling?:** Until now, all data inside our variables lived inside the computer's volatile RAM memory. The exact moment the script closes, that data drops and disappears forever. File Handling allows Python to read from and write directly to permanent physical files on your hard disk (like `.txt`, `.csv`, `.json`), ensuring data survival across application restarts.
* **The Manual Lifecycle Overhead:** Traditionally, to modify a file, you invoke `file = open("path", "mode")`, execute your operations, and you must explicitly invoke `file.close()` at the absolute end.
* **The Resource Leak Danger:** If your program crashes or encounters an exception *before* reaching the `.close()` statement row, that file remains locked and hanging open in system background memory, causing dangerous memory leaks and potential file corruption!

```text
Visual Volatile RAM vs Permanent Storage Matrix:
[ Script Running ] ───> RAM Memory Variables ───> [ Program Closes ] ───> Data Wiped/Lost
[ File Handling  ] ───> Hard Disk File (.txt) ───> [ Program Closes ] ───> Data Saved Safely
```
</details>

---

## 2. 📂 Core Access Stream Modes Matrix (`r` vs `w` vs `a`)

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

When opening a file stream pointer, Python requires you to pass a specific single-character mode string value to declare your operational intent. Choosing the wrong mode can accidentally delete your existing data:
* **Mode `'r'` (Read Only - Default):** Opens an existing file strictly to read its data rows. If the targeted file is missing from the directory path, it throws a `FileNotFoundError` crash pass.
* **Mode `'w'` (Write Only - Overwrite Block):** Opens a file to write data. **Critical Warning:** If the file already exists, `'w'` completely wipes out (erases) all its old content to start fresh. If the file doesn't exist, it programmatically creates a brand-new file slot.
* **Mode `'a'` (Append Only - Continuous Logger):** Opens a file to write data, but instead of wiping out old contents, it appends the new text cleanly onto the absolute end of the file. If the file is missing, it creates it automatically.

```text
📊 Stream Modes Behavior Blueprint:
   open("log.txt", "w") ───> [ Wipes out Old Text Entirely ] ───> Writes fresh new lines
   open("log.txt", "a") ───> [ Keeps Old Text Safe ]         ───> Appends lines onto the end
```
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Simulating access mode validation paths logic
target_file_path = "system_telemetry.log"

print(f"[STREAM_MODE] Opening '{target_file_path}' in 'w' mode will overwrite old records.")
print(f"[STREAM_MODE] Opening '{target_file_path}' in 'a' mode will safely append new records.")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
[STREAM_MODE] Opening 'system_telemetry.log' in 'w' mode will overwrite old records.
[STREAM_MODE] Opening 'system_telemetry.log' in 'a' mode will safely append new records.
```
</details>

---

## 3. 📂 Production Standard Architecture: The Context Manager (`with open()`)

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **What is a Context Manager?:** The `with` keyword initializes an automated runtime context manager shield layout wrapper. It is the absolute industry standard way to interact with files in professional production code environments.
* **The Auto-Closing Law:** Using `with open("file.txt", "r") as file:` completely eliminates the need to call `file.close()` manually. The exact millisecond your code execution leaves the indented block, Python automatically guarantees the file is shut safely, even if the code inside encountered an exception crash midway!

```text
📊 Auto-Closing Structural Block Gateway:
 with open("data.txt", "w") as file_pointer:
 └───> [ Statement Row 1 ] (File Open & Operational)
 └───> [ Statement Row 2 ] (File Open & Operational)
[ Outdent: Main Program Flow continues ] ───> Python auto-shuts data.txt behind the scenes!
```
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Writing data inside a fresh file structure utilizing the with context manager framework
with open("production_output.txt", "w") as file_writer:
    file_writer.write("SYSTEM_STATUS: ONLINE\n")
    file_writer.write("NODES_ACTIVE: 73\n")
# At this absolute point outdent, the file stream is automatically committed and closed safely!

# Re-opening the persistent data file to read its contents back into RAM memory
with open("production_output.txt", "r") as file_reader:
    extracted_file_payload = file_reader.read()

print("--- Extracted Hard Disk File Contents Heap ---")
print(extracted_file_payload)
print("---------------------------------------------")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
--- Extracted Hard Disk File Contents Heap ---
SYSTEM_STATUS: ONLINE
NODES_ACTIVE: 73

---------------------------------------------
```
</details>

---

## 4. 📂 Sequential Stream Traversal Processing (Iterating Rows)

<details>
<summary>💡 <b>Click to view Explanation</b></summary>
<br>

* **The Memory Exhaustion Threat:** Reading an immense 5 GB server log file into RAM all at once using `.read()` will instantly overload your system heap limits and cause a critical out-of-memory infrastructure crash.
* **Line-by-Line Iteration Pattern:** Because file objects in Python operate as native iterators, you can pass them directly into a standard `for` loop. This scans and streams the file line-by-line sequentially, keeping only one single line in memory at any given millisecond. This allows your scripts to safely parse massive datasets of any size with minimal RAM consumption.
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Simulating line-by-line row traversal processing on a mock data array log pipeline
mock_log_lines_dataset = ["ERROR: Ingestion timeout\n", "INFO: Sync complete\n", "WARN: High latency\n"]

print("Simulating High-Performance Line-by-Line Data Streaming Sweep:")
for raw_log_line in mock_log_lines_dataset:
    # Utilizing .strip() method to drop trailing newline whitespace characters (\n) cleanly
    sanitized_row_text = raw_log_line.strip()
    
    if sanitized_row_text.startswith("ERROR"):
        print(f" -> [CRITICAL ALERT] Found Target Row Line: {sanitized_row_text}")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Simulating High-Performance Line-by-Line Data Streaming Sweep:
 -> [CRITICAL ALERT] Found Target Row Line: ERROR: Ingestion timeout
```
</details>
