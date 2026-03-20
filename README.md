# password-checker
This project is a Python-based Password Strength Checker that analyzes user passwords and determines their security level. It checks factors such as password length, use of uppercase and lowercase characters, digits, and special symbols. The tool helps users understand how strong their passwords are and encourages better password security practices.

password = input("Enter your password: ")

score = 0
special_chars = "!@#$%^&*()_+-="

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

strength = (score / 5) * 100
print(f"Strength: {strength}%")

if score <= 2:
    print("Weak Password ❌")
elif score <= 4:
    print("Medium Password ⚠️")
else:
    print("Strong Password ✅")
