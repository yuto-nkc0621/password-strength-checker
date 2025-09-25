# password-strength-checker

import re

def check_password_strength(password):
    length_error = len(password) < 8
    digit_error = re.search(r"\d", password) is None
    uppercase_error = re.search(r"[A-Z]", password) is None
    symbol_error = re.search(r"[!@#$%^&*()_+]", password) is None

    if not length_error and not digit_error and not uppercase_error and not symbol_error:
        return "Strong password"
    else:
        return "Weak password"

user_pass = input("Enter a password to test: ")
print(check_password_strength(user_pass))
