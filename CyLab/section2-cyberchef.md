# Section 2 — CyberChef

> Platform: CyLab Security Academy (picoCTF)  
> Date: 2026-05-22  
> Difficulty: Easy  

---

## Mod 26

**Category:** Cryptography  
**Description:** Decrypt a ROT13-encoded string.

### Solution

The encoded string is passed through ROT13 — a Caesar cipher that shifts each letter by 13 positions. Since the alphabet has 26 letters, applying ROT13 twice returns the original text.

Decoded using CyberChef: `From ROT13` recipe.

**Flag:** `picoCTF{next_time_I'll_use_AES_<hash>}`

### Concepts Learned
- ROT13 is the simplest substitution cipher — each letter is replaced by the one 13 positions ahead
- It's trivially reversible and offers no real security
- CyberChef is a browser-based tool for encoding, decoding, and transforming data

---

## 2warm

**Category:** General Skills  
**Description:** Convert a decimal number to binary.

### Solution

Convert the given decimal number to binary using CyberChef: `To Binary` recipe, or manually:

```python
bin(42)  # Output: '0b101010'
```

**Flag:** `picoCTF{101010}`

### Concepts Learned
- Binary (base 2) is the foundation of all digital computing
- Decimal to binary conversion: repeatedly divide by 2 and track remainders
- CyberChef handles base conversions instantly

---

## Bases

**Category:** General Skills  
**Description:** Decode a Base64-encoded string to find the flag.

### Solution

The encoded string is decoded using CyberChef: `From Base64` recipe.

```bash
# Or in terminal:
echo "<encoded_string>" | base64 -d
```

**Flag:** `picoCTF{l3arn_the_r0p3s_<hash>}`

### Concepts Learned
- Base64 encodes binary data as ASCII text using 64 characters (A–Z, a–z, 0–9, +, /)
- It is NOT encryption — it's encoding, and is trivially reversible
- Commonly used in web tokens, email attachments, and CTF challenges
