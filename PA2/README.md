# EC Curve Parameter Extractor  
### Extract Elliptic Curve (EC-DSA) Parameters From a PEM Certificate  
Author: *<Your Name>*  

---

## 📌 Overview  
This Python script extracts **Elliptic Curve (EC)** parameters from an X.509 certificate (PEM format).  
It detects whether the certificate uses **ECDSA**, and if so, prints:

- Curve name  
- Key size  
- Field characteristic \( p \)  
- Elliptic curve coefficients \( a \) and \( b \)  
- Curve equation in short Weierstrass form  

The script uses the **cryptography** library for parsing certificates and reading EC public keys.

---

## 🔧 Features  
✔ Detects whether a certificate uses **EC-DSA**  
✔ Extracts curve metadata (name, key size)  
✔ Displays parameters of prime-field curves \( \text{GF}(p) \):  
  - Field characteristic \( p \)  
  - Curve coefficients \( a \), \( b \)  
  - Prints the curve equation  
✔ Handles binary-field curves gracefully  
✔ Minimal, clean, and easy to extend  

---

## 📦 Requirements  
Install the required Python package:

```bash
pip install cryptography
