# Python-time
Using time in Python:
def caesar_decrypt(cipher_text, key):
    result = ""
    for char in cipher_text:
        if char.isalpha():
            shift = key % 26
            if char.islower():
                result += chr((ord(char) - ord('a') - shift) % 26 + ord('a'))
            elif char.isupper():
                result += chr((ord(char) - ord('A') - shift) % 26 + ord('A'))
        else:
            result += char
    return result


cipher_text = "Wklv lv d whvw phvvdjh"

print(":\n")
for key in range(1, 26):
    start_time = time.time()  
    decrypted = caesar_decrypt(cipher_text, key)
    end_time = time.time()   
    elapsed = end_time - start_time 
    print(f" {key}: {decrypted}   {elapsed:.6f} "
