🔐 VaultScribe Secure vs Vulnerable Register Flow

This document compares the secure and intentionally vulnerable registration flow implementations in VaultScribe.


---

✅ Secure Register Flow

Uses Laravel ORM / Prepared Statements

Prevents SQL Injection attacks

Strong password validation rules

Weak password blacklist detection

Password peppering + Argon2id hashing

Secure 6-digit OTP generation

OTP expires after 5 minutes

OTP attempt tracking enabled

Proper email validation

Secure session handling



---

❌ Vulnerable Register Flow

Uses raw SQL queries

Vulnerable to SQL Injection

Weak password policy

Plain-text password storage

No password hashing

Weak 4-digit OTP

No OTP expiration

Weak input validation

Insecure authentication flow

Higher brute-force risk



---

🔥 Security Comparison

Feature	Secure Version	Vulnerable Version

SQL Queries	ORM / Prepared Statements	Raw SQL
SQL Injection	Protected	Vulnerable
Password Storage	Argon2id + Pepper	Plain Text
OTP Security	6-digit + Expiry	Weak OTP
Validation	Strong	Weak
Session Security	Secure	Weak



---

🎯 Learning Goal

This comparison demonstrates:

Secure coding practices

Common authentication vulnerabilities

SQL Injection prevention

Secure password handling

OTP security concepts

Secure vs insecure implementation differences


⚠️ Vulnerable examples are intentionally created for AppSec learning purposes only.
