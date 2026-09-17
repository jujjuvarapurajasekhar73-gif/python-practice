# 📥 Input Function in Python

<details open>
<summary><kbd> 📝 Click to Toggle: Notes & Explanation </kbd></summary>
<br>

The `input()` function allows the program to accept user inputs via the keyboard during runtime.
* **Default String Type:** The `input()` function always captures inputs as a **String (`str`)** by default.
* **Typecasting:** If you need to perform calculations on numeric inputs, you must explicitly convert the captured string using functions like `int()` or `float()`.
</details>

<details open>
<summary><kbd> 💻 Click to Toggle: Code Practice </kbd></summary>
<br>

```python
# Capturing a standard string input
fav_language = input("Enter your favorite programming language: ")
print("You entered:", fav_language)

# Capturing numeric input using Typecasting
user_age = int(input("Enter your current age: ")) 
print("Your age next year will be:", user_age + 1)
```
</details>
