# 🧱 Module 21: Object-Oriented Programming (OOPs) Mastery (Part 2A)

This module covers advanced structural reusability frameworks (Inheritance Architecture), code modularity optimization, and enforcement of the DRY law across enterprise applications using Single, Multi-Level, and Multiple Inheritance structures.

---

## 5. 🧱 Inheritance Architecture (Code Reusability & DRY Law)

<details>
<summary>💡 <b>Click to view Deep Explanation & Practical Analogy</b></summary>
<br>

* **What is Inheritance?:** A structural design pattern that allows a brand-new child class (Sub Class) to automatically inherit, adopt, and reuse all fields, variables, and method tools from an existing parent class (Super Class) layout.
* **Why Use It?:** Enforces the absolute DRY (Don't Repeat Yourself) system rule. Instead of copy-pasting identical server configuration lines across 5 separate class files, you define them once inside a master parent class layer.
* **Real-World Corporate Analogy:** Think of a smartphone manufacturing ecosystem. Apple designs a base blueprint called `IPhone_Base` wrapping default hardware features like `camera()`, `battery()`, and `screen()`. Now, when they engineer a child variant called `IPhone_Pro`, they don't redesign the camera or battery from scratch. They simply inherit from `IPhone_Base` for free and focus strictly on adding custom lidar sensors or pro-motion logic.
</details>

<details>
<summary>📊 <b>Click to view General Structural Mapping</b></summary>
<br>

```text
📐 Parent-Child Modularity Mapping:
     ┌─────────────────────────────┐
     │  Parent Class: CloudServer  │ ───> Attributes: ip, status | Method: reboot()
     └──────────────┬──────────────┘
                    │
            Inherited Via Child (extends)
                    │
                    ▼
     ┌─────────────────────────────┐
     │ Child Class: AppServer      │ ───> Gains ip, status, and reboot() instantly!
     └─────────────────────────────┘      └── Adds Custom: deploy_payload()
```
</details>

---

## 5.1 🧱 Types of Inheritance: Single, Multi-Level, & Multiple

Real-world production engineering uses different inheritance strategies based on how deep or complex the data models are. Let's break down the 3 most critical types:

### 🌟 Type A: Single Inheritance
* **Definition:** A clean, straightforward setup where **one child class inherits from exactly one parent class**.
* **Use Case:** Extending a basic system into a specific custom format.

```text
📊 Single Inheritance Flow:
 [ Parent Class: UserAccount ] ───> Inherited By ───> [ Child Class: AdminAccount ]
```

<details>
<summary>💻 <b>Click to view Single Inheritance Enterprise Code</b></summary>
<br>

```python
# Master Parent Class
class BasicUser:
    def __init__(self, username):
        self.name = username
        self.access = "READ_ONLY"

    def display_access_profile(self):
        print(f"[SECURITY] User Profile: '{self.name}' holds access tier: {self.access}")

# Child Class inheriting from BasicUser
class PremiumUser(BasicUser):
    def enable_premium_features(self):
        self.access = "READ_WRITE_EXECUTE"
        print(f"[UPGRADE] VIP Token Validated for '{self.name}'. Upgraded to Premium.")

# Instantiating single inheritance child object
client_profile = PremiumUser("Raja_Shekar_73")
client_profile.display_access_profile() # Running parent method
client_profile.enable_premium_features() # Running child method
client_profile.display_access_profile() # Running parent method again to see the mutation
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
[SECURITY] User Profile: 'Raja_Shekar_73' holds access tier: READ_ONLY
[UPGRADE] VIP Token Validated for 'Raja_Shekar_73'. Upgraded to Premium.
[SECURITY] User Profile: 'Raja_Shekar_73' holds access tier: READ_WRITE_EXECUTE
```
</details>

---

### 🌟 Type B: Multi-Level Inheritance
* **Definition:** A deep chain structural layout where a child class inherits from a parent class, which in turn inherits from another grandparent class!
* **Use Case:** Building continuous vertical feature upgrades over base architectures.

```text
📊 Multi-Level Chain Flow:
 [ Grandparent: Vehicle Plan ] ───> [ Parent: Car Plan ] ───> [ Child: ElectricCar Plan ]
```

<details>
<summary>💻 <b>Click to view Multi-Level Inheritance Enterprise Code</b></summary>
<br>

```python
# Grandparent Class
class HardwareDevice:
    def __init__(self, model_serial):
        self.serial = model_serial
    def boot_power(self):
        print(f"[HARDWARE] Hardware serial {self.serial} spinning up power grids...")

# Parent Class inheriting from HardwareDevice
class ComputingServer(HardwareDevice):
    def allocate_ram(self):
        print(f"[COMPUTE] RAM memory block caches allocated for device serial {self.serial}.")

# Child Class inheriting from ComputingServer (Gains everything above!)
class AIWorkerNode(ComputingServer):
    def run_inference_model(self):
        print(f"[AI_NODE] Launching neural network matrix math on top of serial {self.serial} clusters.")

# Testing the multi-level inheritance pipeline trace
ai_cluster = AIWorkerNode("GPU-73440-NODE")
ai_cluster.boot_power()       # Executing Grandparent logic
ai_cluster.allocate_ram()     # Executing Parent logic
ai_cluster.run_inference_model() # Executing Child logic
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
[HARDWARE] Hardware serial GPU-73440-NODE spinning up power grids...
[COMPUTE] RAM memory block caches allocated for device serial GPU-73440-NODE.
[AI_NODE] Launching neural network matrix math on top of serial GPU-73440-NODE clusters.
```
</details>

---

### 🌟 Type C: Multiple Inheritance
* **Definition:** A unique configuration where **a single child class inherits from multiple, independent parent classes simultaneously**.
* **Use Case:** Combining completely separate functional toolsets into a single powerful utility block.

```text
📊 Multiple Parents Injection Flow:
 [ Parent 1: DatabaseTool ] ──┐
                              ├─── Inherited By ───> [ Child Class: BackendOrchestrator ]
 [ Parent 2: NetworkSecurity] ──┘
```

<details>
<summary>💻 <b>Click to view Multiple Inheritance Enterprise Code</b></summary>
<br>

```python
# Parent Class 1: Handles Storage Systems
class StorageEngine:
    def save_record(self, data_payload):
        print(f"[STORAGE] Writing token data '{data_payload}' straight into hard disk sectors.")

# Parent Class 2: Handles Security Infrastructure
class EncryptionGate:
    def encrypt_payload(self, text):
        print(f"[SECURITY] Running AES-256 cipher blocks on target raw input string data.")
        return f"ENCRYPTED_<{text}>"

# Child Class combining BOTH parent capabilities into one single class framework
class SecureBackupManager(StorageEngine, EncryptionGate):
    def process_secure_backup(self, raw_data):
        print(f"[ORCHESTRATOR] Launching secure automated pipeline for data...")
        # Accessing tools from Parent 2
        secured_string = self.encrypt_payload(raw_data)
        # Accessing tools from Parent 1
        self.save_record(secured_string)

# Deploying multiple inheritance objects
backup_agent = SecureBackupManager()
backup_agent.process_secure_backup("CONFIDENTIAL_BALANCE_DATA_73")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
[ORCHESTRATOR] Launching secure automated pipeline for data...
[SECURITY] Running AES-256 cipher blocks on target raw input string data.
[STORAGE] Writing token data 'ENCRYPTED_<CONFIDENTIAL_BALANCE_DATA_73>' straight into hard disk sectors.
```
</details>
---

## 6. ⚙️ Method Overriding & The `super()` Escalation Engine

<details>
<summary>💡 <b>Click to view Deep Explanation & Practical Analogy</b></summary>
<br>

* **What is Method Overriding?:** Method Overriding happens when a child class writes a method with the exact same name as one already defined inside its parent class. When an object of the child class calls this method, Python executes the child's custom version, completely hiding the parent's default behavior.
* **The `super()` Keyword:** A specialized built-in proxy indicator tool. It allows a child class to call and run code from the parent class's version of a method *before* executing its own custom lines.
* **Why Combine Them?:** Crucial for constructor extensions. Instead of entirely throwing away the parent class constructor logic, the child calls `super().__init__()` to load default settings first, and then adds its own custom attributes underneath, preventing structural gaps.
* **Real-World Corporate Analogy:** Think of an enterprise payroll system. You have a `BaselineEmployee` class with a method `calculate_bonus()`. For a `Manager` child class, you override `calculate_bonus()` to add custom stock options. By using `super().calculate_bonus()`, you fetch the base salary calculation first and then add the performance bonus on top, preventing calculation errors.
</details>

<details>
<summary>📊 <b>Click to view Method Overriding Process Flow</b></summary>
<br>

```text
⚙️ Method Overriding Lifecycle Map:
 [ PrivilegedAdminAccount.render_dashboard() ]
        │
        ├─── Step 1: Invokes super().render_dashboard() ───> [ Runs Parent Code Block ]
        │                                                           │
        │                                                    (Returns to Child Thread)
        │                                                           │
        │                                                           ▼
        └─── Step 2: Executes custom child override lines ───> [ Runs Elevated Core Panels ]
```
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
class BaselineUserAccount:
    def __init__(self, username):
        self.user = username
        self.clearance = "GUEST"
        
    def render_dashboard(self):
        print(f"[BASE] Rendering default interface options for account: {self.user}")

class PrivilegedAdminAccount(BaselineUserAccount):
    def __init__(self, username, secure_token):
        # Escalating inputs up to the parent constructor to map the user name box first
        super().__init__(username)
        # Extending local state attributes with custom parameters unique to the child
        self.clearance = "ROOT_ADMIN"
        self.token = secure_token
        
    def render_dashboard(self):
        # 1. Executing default parent visualization first via super()
        super().render_dashboard()
        # 2. Injecting custom child override additions underneath
        print(f"[OVERRIDE] Injecting elevated administrative control panels. Clearance: {self.clearance}")

# Triggering the overridden architecture execution pass
admin_profile = PrivilegedAdminAccount("Raja_Shekar_73", "SECURE_SSL_TOKEN_XYZ")
admin_profile.render_dashboard()
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
[BASE] Rendering default interface options for account: Raja_Shekar_73
[OVERRIDE] Injecting elevated administrative control panels. Clearance: ROOT_ADMIN
```
</details>

---

## 7. 🎭 Polymorphism & Dynamic Interfaces (Dynamic Typing Power)

<details>
<summary>💡 <b>Click to view Deep Explanation & Practical Analogy</b></summary>
<br>

* **What is Polymorphism?:** Derived from Greek words meaning **"Many Shapes"**. It is a core programming technique where different classes can share the exact same method name, but each class executes that method with completely unique internal behaviors.
* **The Interface Paradigm:** Allows a single manager loop stream to process a mixed list of different objects seamlessly, calling the same method name on all of them without needing to check their specific data types beforehand.
* **Real-World Device Analogy:** Think of a standard universal remote controller button called `power_on()`. If you send the command to a Television object, it turns on a screen display. If you send the exact same command to an Air Conditioner object, it spins up a cooling motor engine. The method name is identical (`power_on()`), but the internal technical execution changes entirely based on *which* object catches the signal!
</details>

<details>
<summary>📊 <b>Click to view Polymorphic Action Blueprint</b></summary>
<br>

```text
🎭 Universal Controller Interface:
 Loop Traversal ───> Calls .execute_export_stream() 
                         ├─── Object A (Billing) ───> Outputs CSV Text Layout
                         └─── Object B (Database)───> Fires Encrypted SQL Queries
```
</details>

<details>
<summary>💻 <b>Click to view Enterprise Code</b></summary>
<br>

```python
# Engineering independent classes sharing an identical interface signature name
class AutomatedBillingLogger:
    def execute_export_stream(self):
        return "Streaming financial ledger invoices straight to CSV file storage."

class SecureDatabaseLogger:
    def execute_export_stream(self):
        return "Executing encrypted SQL queries to update core server tables."

# Creating a mixed array list containing completely different object models
active_system_loggers_pool = [AutomatedBillingLogger(), SecureDatabaseLogger()]

print("Launching Polymorphic Interface Looping Sweep:")
# A single manager loop invokes the same method name across different object layers
for single_logger_object in active_system_loggers_pool:
    diagnostic_result = single_logger_object.execute_export_stream()
    print(f" -> Loop Progress Tracking Logs: {diagnostic_result}")
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
Launching Polymorphic Interface Looping Sweep:
 -> Loop Progress Tracking Logs: Streaming financial ledger invoices straight to CSV file storage.
 -> Loop Progress Tracking Logs: Executing encrypted SQL queries to update core server tables.
```
</details>
