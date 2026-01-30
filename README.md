# idor-broken-access-control
# IDOR – Broken Access Control (Case Study)

## Summary
## Summary
A Broken Access Control vulnerability in the form of an Insecure Direct Object Reference (IDOR) was identified due to the absence of proper server-side authorization checks. This allowed an authenticated user to access data belonging to other users by manipulating object reference parameters.

## Vulnerability Type
Broken Access Control – IDOR (Horizontal Privilege Escalation)

## Severity
- Risk Rating: High
- CVSS v3.1 Base Score: 7.5

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
An attacker could exploit this vulnerability to perform horizontal privilege escalation, leading to unauthorized access to sensitive user data. In real-world applications, this could result in data confidentiality breaches, user privacy violations, and potential compliance issues.


## Remediation
- Implement strict server-side authorization checks for all object-level access.
- Ensure object ownership validation is enforced before returning sensitive data.
- Apply the principle of least privilege when designing access control mechanisms.


## Proof of Concept
Authorized Access- logged in with user credentials 
![image alt](https://github.com/pranaycs/idor-broken-access-control/blob/382e5e19dcf4efa91345291488a229a29aa8d66e/Authorized.png)

modified the id  to "Carlos" to get the API key of carlos which is not authorized
![image alt](https://github.com/pranaycs/idor-broken-access-control/blob/382e5e19dcf4efa91345291488a229a29aa8d66e/idor-modified-request.png)

Since there is no server side checks for object references.Got the API key of carlos
![image alt](https://github.com/pranaycs/idor-broken-access-control/blob/382e5e19dcf4efa91345291488a229a29aa8d66e/unauthorized-access.png)


## Disclaimer
This assessment was performed in a controlled and legal lab environment strictly for educational and research purposes.
