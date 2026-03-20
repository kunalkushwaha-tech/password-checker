# 🔐 Password Strength Checker

This project is a Python-based tool that analyzes user passwords to determine their security level based on length, casing, digits, and special characters.

## 💻 How it Works (Logic)

```python
password = input("Enter your password: ")
score = 0
special_chars = "!@#$%^&*()_+-="

# Criteria Checks
if len(password) >= 8:
    score += 1
if any(char.isupper() for char in password):
    score += 1
if any(char.islower() for char in password):
    score += 1
if any(char.isdigit() for char in password):
    score += 1
if any(char in special_chars for char in password):
    score += 1

# Strength Calculation
strength = (score / 5) * 100
print(f"Strength: {strength}%")

# Feedback
if score <= 2:
    print("Weak Password ❌")
elif score <= 4:
    print("Medium Password ⚠️")
else:
    print("Strong Password ✅")
