# 🧱 Module 21: Object-Oriented Programming (OOPs) Mastery 

This module covers advanced application data protection layers (Encapsulation Architecture), structural data sandboxing, and access control modifiers using Public, Protected, and Private variables.

---

## 8. 🔒 Encapsulation Architecture (Data Sandboxing & Privacy Rules)

<details>
<summary>💡 <b>Click to view Deep Explanation & Practical Analogy</b></summary>
<br>

* **What is Encapsulation?:** Encapsulation is the process of bundling an object's sensitive data variables (Attributes) and behavior methods together into a single secure package, while strictly restricting direct access from external code blocks.
* **Why Use It?:** Prevents external scripts from accidentally or maliciously overwriting internal object variables directly, which can bypass safety parameters and break business logic constraints.
* **Real-World Capsule Analogy:** Think of a medical capsule pill. The chemical medicine powders are securely sealed inside the outer capsule shell wrapper. You cannot touch or alter the raw powder ingredients directly; you must swallow the capsule as a whole, allowing it to release its contents through a controlled safe path.
</details>

<details>
<summary>📊 <b>Click to view Data Sandboxing Block Gateway</b></summary>
<br>

```text
🔒 Secure Encapsulated Object Shell:
  External Code ───❌ Direct Access Attempt ───❌───> [ Private Data Box: __balance ]
  External Code ───✔️ Authorized Access Gate ───✔️───> [ Method: get_balance() ] ───> Returns Data Safely
```
</details>

---

## 8.1 🔒 Python Access Modifiers: Public vs Protected vs Private

Python enforces access boundaries on variables and methods using a naming convention rule based on single or double underscore prefixes:

### 🌟 1. Public Attributes (No Underscore)
* **Rule:** Accessible from anywhere inside or outside the class framework completely without any restrictions.
* **Syntax:** `self.name = "Raja"`

### 🌟 2. Protected Attributes (Single Underscore `_`)
* **Rule:** Acts as a warning sign. It signals to other developers that this variable is internal and should **only** be accessed within this class or its sub-classes (child classes). However, Python does not physically block external access.
* **Syntax:** `self._database_url = "http://..."`

### 🌟 3. Private Attributes (Double Underscore `__`)
* **Rule:** Strictly locked down and sandboxed. These variables are completely invisible and unreachable from outside the class scope. Attempting direct access throws an immediate `AttributeError` crash loop.
* **Syntax:** `self.__account_balance = 50000.0`
</details>

<details>
<summary>💻 <b>Click to view Access Control Modifiers Enterprise Code</b></summary>
<br>

```python
class SecureVault:
    def __init__(self, owner, secret_key):
        self.vault_owner = owner         # Public Attribute: Free access
        self._vault_tier = "GOLD_LEVEL"   # Protected Attribute: Internal warning
        self.__secret_pin = secret_key   # Private Attribute: Strictly sandboxed

    def reveal_pin_securely(self):
        # Internal methods can read private variables without restriction
        return f"[VAULT_SYSTEM] PIN verification success: {self.__secret_pin}"

# Deploying the encapsulated vault object instance
my_vault = SecureVault("Raja_Shekar_73", 7344)

print("--- Testing Access Modifier Boundaries ---")
print(f"Reading Public Box:   {my_vault.vault_owner}")
print(f"Reading Protected Box: {my_vault._vault_tier}")

try:
    # Attempting to force access straight into the private box boundary
    print(my_vault.__secret_pin)
except AttributeError as caught_error:
    print(f"[SECURITY_INTERCEPT] Direct access blocked: {caught_error}")

# Reading private data cleanly via an authorized class method gateway
print(my_vault.reveal_pin_securely())
```
</details>

<details>
<summary>🖥️ <b>Click to view Expected Output</b></summary>
<br>

```text
--- Testing Access Modifier Boundaries ---
Reading Public Box:   Raja_Shekar_73
Reading Protected Box: GOLD_LEVEL
[SECURITY_INTERCEPT] Direct access blocked: 'SecureVault' object has no attribute '__secret_pin'
[VAULT_SYSTEM] PIN verification success: 7344
```
</details>
