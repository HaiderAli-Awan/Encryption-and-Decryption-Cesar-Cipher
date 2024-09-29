def encrypt(text, shift):
    result = ""
    
    for char in text:
        if char.isalpha():
            # Shift character
            start = ord('A') if char.isupper() else ord('a')
            result += chr((ord(char) - start + shift) % 26 + start)
        else:
            result += char  # Non-alphabetic characters are not changed
            
    return result

def decrypt(text, shift):
    return encrypt(text, -shift)  # Decrypting is the same as encrypting with a negative shift

def brute_force_decrypt(text):
    for shift in range(1, 26):
        decrypted_text = decrypt(text, shift)
        print(f"Shift {shift}: {decrypted_text}")

# Example usage
if __name__ == "__main__":
    original_text = input("Enter the text to encrypt: ")
    shift_value = int(input("Enter the shift value (1-25): "))
    
    encrypted_text = encrypt(original_text, shift_value)
    print(f"Encrypted: {encrypted_text}")
    
    decrypted_text = decrypt(encrypted_text, shift_value)
    print(f"Decrypted: {decrypted_text}")
    
    print("\nBrute-force Decryption:")
    brute_force_decrypt(encrypted_text)

