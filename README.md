# PRODIGY_Cybersecurity_Task1
def caesar_cipher(text, shift, mode):
    result = ""

    for char in text:
        if char.isalpha():
            start = ord('A') if char.isupper() else ord('a')
            if mode == "encrypt":
                result += chr((ord(char) - start + shift) % 26 + start)
            else:
                result += chr((ord(char) - start - shift) % 26 + start)
        else:
            result += char

    return result


message = input("Enter message: ")

while True:
    shift_input = input("Enter shift value (number only): ")
    if shift_input.isdigit():
        shift = int(shift_input)
        break
    else:
        print("❌ Invalid input! Please enter a number.")

choice = input("Encrypt or Decrypt? (e/d): ")

if choice.lower() == 'e':
    print("Encrypted Text:", caesar_cipher(message, shift, "encrypt"))
elif choice.lower() == 'd':
    print("Decrypted Text:", caesar_cipher(message, shift, "decrypt"))
else:
    print("❌ Invalid choice")
