# Caesar Cipher Encryption and Decryption

def encrypt(text, shift):
    result = ""
    for char in text:
        if char.isalpha():              # Check if character is a letter
            if char.isupper():          # Encrypt uppercase letters
                result += chr((ord(char) - ord('A') + shift) % 26 + ord('A'))
            else:                       # Encrypt lowercase letters
                result += chr((ord(char) - ord('a') + shift) % 26 + ord('a'))
        else:
            result += char              # Keep spaces and symbols unchanged
    return result


def decrypt(text, shift):
    result = ""
    for char in text:
        if char.isalpha():              # Check if character is a letter
            if char.isupper():          # Decrypt uppercase letters
                result += chr((ord(char) - ord('A') - shift) % 26 + ord('A'))
            else:                       # Decrypt lowercase letters
                result += chr((ord(char) - ord('a') - shift) % 26 + ord('a'))
        else:
            result += char              # Keep spaces and symbols unchanged
    return result


# Main Program
message = input("Enter the message: ")
shift = int(input("Enter the shift value: "))

encrypted = encrypt(message, shift)
decrypted = decrypt(encrypted, shift)

print("\nOriginal Message :", message)
print("Encrypted Message:", encrypted)
print("Decrypted Message:", decrypted)<img width="917" height="600" alt="Screenshot 2026-07-16 135706" src="https://github.com/user-attachments/assets/d05e98e6-b261-415a-8c60-818570dc87b3" />

