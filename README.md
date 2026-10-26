# Lab-Exercise-4---Vigenere-cipher
## Aim
To develop a simple C program to implement Vigenere Cipher. 
## Procedure
```
1. Design of Vigenere Cipher algorithnm
2. Implementation using C or pyhton code
3.  The Vigenere cipher is a method of encrypting alphabetic text by using a series of different Caesar ciphers based on the letters of a keyword.
4.  It is a simple form of polyalphabetic substitution.To encrypt, a table of alphabets can be used, termed a Vigenere square, or Vigenere table.
5.  It consists of the alphabet written out 26 times in different rows, each alphabet shifted cyclically to the left compared to the previous alphabet, corresponding to the 26 possible Caesar ciphers.
6.  At different points in the encryption process, the cipher uses a different alphabet from one of the rows used. The alphabet 
at each point depends on a repeating keyword. 
```

## PROGRAM:
```
def vigenere_encrypt(message, key):
    result = ""
    key = key.upper()
    j = 0

    for ch in message.upper():
        if ch.isalpha():
            shift = ord(key[j % len(key)]) - ord('A')
            result += chr((ord(ch) - ord('A') + shift) % 26 + ord('A'))
            j += 1
        else:
            result += ch

    return result


def vigenere_decrypt(message, key):
    result = ""
    key = key.upper()
    j = 0

    for ch in message.upper():
        if ch.isalpha():
            shift = ord(key[j % len(key)]) - ord('A')
            result += chr((ord(ch) - ord('A') - shift) % 26 + ord('A'))
            j += 1
        else:
            result += ch

    return result


# Main Program
message = input("Enter plaintext: ")
key = input("Enter key: ")

if key.isalpha():
    encrypted = vigenere_encrypt(message, key)
    print("Encrypted text:", encrypted)

    decrypted = vigenere_decrypt(encrypted, key)
    print("Decrypted text:", decrypted)
else:
    print("Key must contain only alphabets.")
```
## Output
<img width="1286" height="168" alt="image" src="https://github.com/user-attachments/assets/fdec7acb-357e-4e12-88e9-7dbef63f17d8" />

## Result
The program executed successfully.
