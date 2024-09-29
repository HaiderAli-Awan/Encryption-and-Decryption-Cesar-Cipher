# Encryption-and-Decryption-Cesar-Cipher
**Caesar Cipher Implementation in Python
Overview**
This repository contains a Python implementation of the Caesar cipher, a simple and widely known encryption technique. The program provides functionality for encrypting and decrypting messages using a specified shift value, as well as a brute-force method to attempt decryption by testing all possible shift values.

**Features**
**Encryption: **Convert plaintext into ciphertext using a specified shift.
**Decryption:** Convert ciphertext back into plaintext using the same shift.
**Brute-force Decryption:** Automatically attempts to decrypt the ciphertext with all possible shifts (1-25).
**How to Use**

Clone this repository to your local machine:
bash
Copy code
**git clone https://github.com/yourusername/caesar-cipher.git
cd caesar-cipher**
Run the script:

bash
Copy code
python caesar_cipher.py
Follow the prompts to:

Enter the text you want to encrypt.
Enter the shift value (an integer between 1 and 25).
The script will display the encrypted text, the decrypted text, and the results of the brute-force decryption.

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
python
Copy code
if __name__ == "__main__":
    original_text = input("Enter the text to encrypt: ")
    shift_value = int(input("Enter the shift value (1-25): "))
    
    encrypted_text = encrypt(original_text, shift_value)
    print(f"Encrypted: {encrypted_text}")
    
    decrypted_text = decrypt(encrypted_text, shift_value)
    print(f"Decrypted: {decrypted_text}")
    
    print("\nBrute-force Decryption:")
    brute_force_decrypt(encrypted_text)
Conclusion
This implementation provides a straightforward way to understand the principles of the Caesar cipher. It demonstrates basic encryption and decryption techniques while also allowing users to explore brute-force methods for deciphering messages.

Feel free to modify and expand upon this code as you explore more advanced cryptographic techniques!
