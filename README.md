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


Code Breakdown
Functions
encrypt(text, shift)

Parameters:
text (str): The plaintext message to be encrypted.
shift (int): The number of positions to shift each letter.
Returns: The encrypted text (ciphertext).
Logic:
Iterates through each character in the input text.
If the character is an alphabet letter, it shifts the character by the specified amount, preserving the case.
Non-alphabetic characters remain unchanged.
decrypt(text, shift)

Parameters:
text (str): The ciphertext to be decrypted.
shift (int): The number of positions to shift each letter back.
Returns: The decrypted text (plaintext).
Logic: Calls the encrypt function with a negative shift value.
brute_force_decrypt(text)

Parameters:
text (str): The ciphertext to be decrypted.
Returns: None. Prints all possible decryptions.
Logic: Iterates through all possible shifts from 1 to 25 and prints the decrypted output for each shift.
Example Usage
The main block of the code allows users to interactively input their text and desired shift value. Upon running the script, users will see:

The encrypted output.
The decrypted output using the same shift.
The results of brute-force attempts to decrypt the ciphertext.
