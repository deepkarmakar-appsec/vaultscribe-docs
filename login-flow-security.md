# 🔐 VaultScribe Secure vs Vulnerable Login Flow

This document compares the login authentication flow between:

- `vaultscribe-secure`
- `vaultscribe-vulnerable`

The login system is implemented inside the Laravel `AuthController`.

---

# ✅ vaultscribe-secure

- Uses Laravel ORM / Prepared Statements
- Prevents SQL Injection attacks
- Uses `Hash::check()` for secure password verification
- Password peppering with HMAC-SHA256
- CAPTCHA protection after multiple failed attempts
- Login attempt tracking enabled
- Suspicious login detection
- Security activity logging enabled
- Secure session regeneration
- Uses Laravel `Auth::login()`
- Better brute-force protection
- Safer authentication flow
- Improved session handling
- Generic authentication error handling
- Better credential protection
- Supports optional 2FA challenge flow

---

# ❌ vaultscribe-vulnerable

- Uses raw SQL queries
- Vulnerable to SQL Injection
- Plain-text password comparison
- No password hashing
- No password peppering
- Missing session regeneration
- Uses insecure `loginUsingId()` flow
- No CAPTCHA protection
- No rate limiting
- No login monitoring
- No suspicious activity detection
- Weak brute-force protection
- Higher credential stuffing risk
- Weak session handling
- Insecure authentication design
- Possible authentication bypass
- Possible privilege escalation via SQL Injection
- Weak overall login security

---

# 🔥 Security Comparison

| Feature | vaultscribe-secure | vaultscribe-vulnerable |
|---|---|---|
| SQL Queries | ORM / Prepared Statements | Raw SQL |
| SQL Injection | Protected | Vulnerable |
| Password Verification | `Hash::check()` | Plain Comparison |
| Password Protection | Pepper + Hashing | Plain Text |
| CAPTCHA | Enabled | Missing |
| Rate Limiting | Enabled | Missing |
| Login Monitoring | Activity Logging | Missing |
| Suspicious Login Detection | Enabled | Missing |
| Brute-force Protection | Stronger | Weak |
| Session Regeneration | Enabled | Missing |
| Authentication Flow | `Auth::login()` | `loginUsingId()` |
| Session Security | Secure | Weak |
| 2FA Support | Enabled | Missing |

---

# ⚠️ Possible Attack Scenarios

The vulnerable login flow may allow:

- SQL Injection attacks
- Authentication bypass
- Privilege escalation
- Session fixation attacks
- Brute-force attacks
- Credential stuffing attacks
- Weak authentication abuse
- User account compromise
- Weak session management abuse

---

# 🎯 Learning Goal

This comparison demonstrates:

- Secure coding practices
- Common authentication vulnerabilities
- SQL Injection prevention
- Secure password verification
- Session fixation prevention
- Brute-force mitigation
- Secure Laravel authentication
- Authentication hardening
- Secure vs insecure implementation differences

⚠️ Vulnerable examples are intentionally created for AppSec learning purposes only.
