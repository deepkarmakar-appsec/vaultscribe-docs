🔐 VaultScribe Secure vs Vulnerable OTP Flow

This document compares the OTP verification flow between:

vaultscribe-secure

vaultscribe-vulnerable



---

✅ vaultscribe-secure

Uses Laravel ORM / Prepared Statements

Prevents SQL Injection attacks

Uses hashed OTP verification

Secure 6-digit OTP validation

OTP expires after 5 minutes

OTP attempt tracking enabled

Secure session regeneration

Uses Laravel Auth system

Better session validation

Safer authentication flow



---

❌ vaultscribe-vulnerable

Uses raw SQL queries

Vulnerable to SQL Injection

Plain-text OTP comparison

Weak OTP protection

Missing session regeneration

Uses insecure manual authentication flow

Weak session handling

Higher brute-force risk

Manual database queries

Weaker authentication security



---

🔥 Security Comparison

Feature	vaultscribe-secure	vaultscribe-vulnerable

SQL Queries	ORM / Prepared Statements	Raw SQL
SQL Injection	Protected	Vulnerable
OTP Verification	Hash::check()	Plain Comparison
OTP Security	Expiry + Attempts	Weak OTP
Session Regeneration	Enabled	Missing
Authentication Flow	Auth::login()	loginUsingId()
Session Security	Secure	Weak



---

🎯 Learning Goal

This comparison demonstrates:

Secure coding practices

Common authentication vulnerabilities

SQL Injection prevention

OTP security concepts

Session fixation prevention

Secure Laravel authentication

Secure vs insecure implementation differences


⚠️ Vulnerable examples are intentionally created for AppSec learning purposes only.
