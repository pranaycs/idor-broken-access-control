# idor-broken-access-control
# IDOR – Broken Access Control (Case Study)

## Summary
An Insecure Direct Object Reference (IDOR) vulnerability was identified due to missing server-side authorization checks, allowing unauthorized access to other users’ data.

## Vulnerability Type
Broken Access Control – IDOR (Horizontal Privilege Escalation)

## Environment
- Platform: PortSwigger Web Security Academy
- Tools Used: Burp Suite Community
- Testing Type: Manual Web Application Testing

## Steps to Reproduce
1. Logged in as an authenticated low-privileged user.
2. Intercepted the HTTP request responsible for retrieving user account information.
3. Identified a user-controlled object reference parameter in the request.
4. Modified the object reference to another valid identifier.
5. Successfully accessed data belonging to another user without authorization.

## Impact
Exploitation of this vulnerability could allow an attacker to access sensitive user information, resulting in confidentiality and privacy violations. In a real-world scenario, this may also lead to regulatory and compliance risks.

## Remediation
- Enforce server-side authorization checks for all object references.
- Validate user ownership before granting access to resources.
- Avoid relying on client-side parameters for access control decisions.

## Proof of Concept
Screenshots demonstrating authorized access, parameter manipulation, and unauthorized data access are provided below.

## Disclaimer
This assessment was performed in a controlled and legal lab environment strictly for educational and research purposes.
