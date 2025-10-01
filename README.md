# Cryptographic-File-Encryption-and-Decryption-with-RSA-DES-GUI-Creation-and-Implementation-
A Python-based project implementing RSA (asymmetric) and DES (symmetric) encryption, with performance testing to measure encryption/decryption time and evaluate how file compression sizes change after encryption
# 🔐 Cryptography Encryption and Decryption with RSA & DES (Python GUI)

This project demonstrates the implementation of **RSA (asymmetric) and DES (symmetric) encryption/decryption** using Python with GUI interfaces. It includes **encryption/decryption**, **performance testing (time analysis)**, and **file compression size comparison**.

## 🚀 Features
- RSA and DES encryption & decryption
- GUI built with [CustomTkinter](https://github.com/TomSchimansky/CustomTkinter)
- Encryption time measurement
- File compression size analysis

## 🛠️ Tools & Libraries
- [Python 3.x](https://www.python.org/downloads/)  
- [CustomTkinter](https://github.com/TomSchimansky/CustomTkinter)  
- [PyCryptodome](https://pycryptodome.readthedocs.io/)  
- [NumPy](https://numpy.org/)  

Install dependencies:
```bash
pip install customtkinter pycryptodome numpy
📦 Cryptography-RSA-DES
 ┣ 📜 rsa_gui.py
 ┣ 📜 des_gui.py
 ┣ 📜 README.md
 ┣ 📂 screenshots
 ┗ 📂 test_files

Codes for RSA
from Crypto.PublicKey import RSA
from Crypto.Cipher import PKCS1_OAEP

# Key generation
key = RSA.generate(2048)
private_key = key.export_key()
public_key = key.publickey().export_key()

# Encrypt
cipher = PKCS1_OAEP.new(RSA.import_key(public_key))
ciphertext = cipher.encrypt(b"HELLO RSA")

# Decrypt
decipher = PKCS1_OAEP.new(RSA.import_key(private_key))
plaintext = decipher.decrypt(ciphertext)
print("Decrypted:", plaintext.decode())

Codes for DES
from Crypto.Cipher import DES
from Crypto.Random import get_random_bytes

# Key (8 bytes)
key = get_random_bytes(8)
cipher = DES.new(key, DES.MODE_ECB)

# Encrypt / Decrypt
plaintext = b"HELLO123"  # multiple of 8
ciphertext = cipher.encrypt(plaintext)
decrypted = DES.new(key, DES.MODE_ECB).decrypt(ciphertext)
print("Decrypted:", decrypted.decode())

 Codes for GUI Interface
import customtkinter as ctk

def encrypt_action():
    pass  # call RSA/DES functions here

app = ctk.CTk()
app.title("Cryptography Tool")

label = ctk.CTkLabel(app, text="RSA & DES Encryption/Decryption")
label.pack(pady=10)

button = ctk.CTkButton(app, text="Encrypt File", command=encrypt_action)
button.pack(pady=10)

app.mainloop()

Performance

Execution time measured with Python’s time module

Compression analysis performed before & after encryption

📸 Screenshots

(Add GUI screenshots here)

👤 Author

Bashiru Damoah

📜 License
