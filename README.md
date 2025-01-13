# Bypass 403 Forbidden 🚪🔓

The **403 Forbidden** status code is often encountered when attempting to access restricted resources. However, there are techniques that attackers or penetration testers use to bypass these restrictions under specific conditions.

---

## 🚀 What is 403 Forbidden?

The **403 Forbidden** HTTP response status indicates that the server understood the request but refuses to authorize it. Common reasons include:
1. IP blacklisting or geo-restrictions.
2. Insufficient permissions.
3. WAF (Web Application Firewall) rules.

---

## 🎯 Common Techniques for Bypassing 403

### 1. **Modify HTTP Headers**
- Sometimes, servers block requests based on the User-Agent or Referer headers.
- Use tools like `curl` or Burp Suite to modify headers.

**Example (User-Agent Bypass):**
```bash
curl -X GET https://example.com/forbidden-resource -H "User-Agent: Mozilla/5.0"

Example (Referer Bypass):
curl -X GET https://example.com/forbidden-resource -H "Referer: https://example.com"

2. URL Encoding

    Encoding special characters in the URL can bypass certain filters.
    For example:https://example.com/forbidden-resource
can become:https://example.com/%66%6F%72%62%69%64%64%65%6E-resource

3. Adding a Trailing Slash

    Some servers treat URLs with a trailing slash differently.
https://example.com/forbidden-resource/
4. IP Address Instead of Domain Name

    Accessing the resource directly via the server's IP address may bypass domain-specific restrictions:
http://192.168.1.1/forbidden-resource

5. Alternate HTTP Methods

    Instead of using the default GET method, try others like POST, HEAD, or OPTIONS:curl -X POST https://example.com/forbidden-resource

🌟 Visual Demo
<div align="center"> <img src="https://media.giphy.com/media/3o7abldj0b3rxrZUxW/giphy.gif" width="400" alt="Bypass 403 Animation"/> </div>

🛠️ Tools for Bypassing 403

    Burp Suite:
        Modify headers and analyze server responses.
    FFUF:
        Automate bypass attempts with fuzzing
ffuf -u https://example.com/FUZZ -w wordlist.txt -H "User-Agent: Mozilla/5.0"


3. curl:

    Lightweight and flexible for quick testing.

📖 Learn More

    HTTP Status Code 403 (MDN)
    Pentester Academy: Bypass Techniques



