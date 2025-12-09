# PA-2: Elliptic Curve Parameter Extraction

This project extracts elliptic curve parameters from an X.509 certificate using Python.  
The script detects whether the certificate uses **ECDSA**, identifies the curve name, and prints:

- Field characteristic \( p \)  
- Curve coefficients \( a \) and \( b \)  
- Elliptic curve equation in short Weierstrass form:

\[
y^2 = x^3 + ax + b \pmod p
\]

---

## Requirements

Install dependencies:

```bash
pip install cryptography ecdsa
```

Python version: **3.8+**

---

## Usage

Export a certificate in `.pem` format and run:

```bash
python extract_ec_curve.py certificate.pem
```

---

## Example Output

```
Public Key Algorithm: ECDSA
Elliptic Curve Name: prime256v1

Field characteristic p: 0xffffffff00000001000000000000000000000000ffffffffffffffffffffffff
Coefficient a:        0xffffffff00000001000000000000000000000000fffffffffffffffffffffffc
Coefficient b:        0x5ac635d8aa3a93e7b3ebbd55769886bc651d06b0cc53b0f63bce3c3e27d2604b

Elliptic Curve: y^2 = x^3 + a·x + b (mod p)
```

---

## Notes

Common detected curves:

| Curve | Standard Name | Security Level |
|-------|---------------|----------------|
| secp256r1 | NIST P-256 | ~128-bit |
| secp384r1 | NIST P-384 | ~192-bit |
| secp521r1 | NIST P-521 | ~256-bit |

---

## Author

\<Your Name\> — PA-2 Submission
