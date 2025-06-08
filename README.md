import random
import string

def generate_password():
    length = int(input("Enter password length: "))
    use_uppercase = input("Include uppercase letters? (y/n): ").lower() == 'y'
    use_numbers = input("Include numbers? (y/n): ").lower() == 'y'
    use_symbols = input("Include symbols? (y/n): ").lower() == 'y'

    characters = string.ascii_lowercase
    if use_uppercase:
        characters += string.ascii_uppercase
    if use_numbers:
        characters += string.digits
    if use_symbols:
        characters += string.punctuation

    if not characters:
        print("No character types selected. Cannot generate password.")
        return
    password = ''.join(random.choice(characters) for _ in range(length))
    print("Generated Password:", password)
generate_password()

output:
Enter password length: 12
Include uppercase letters? (y/n): y
Include numbers? (y/n): y
Include symbols? (y/n): y
Generated Password: T8&kxZb@P#2
