# TryHackMe Pre-Security: HTTP in Detail Write-up

**Platform**: TryHackMe  
**Path**: Pre-Security → How the Web Works  
**Difficulty**: Very Easy  
**Completed**: March 23, 2026  
**Link**: https://tryhackme.com/room/httpindetail

## TL;DR
Learned HTTP protocol fundamentals including methods, status codes, headers, and cookies. Used Burp Suite to intercept requests and found the final flag.

## Enumeration
Deployed the TryHackMe VM and accessed the web server. Basic HTTP request showed standard 200 OK response with HTML content.

```bash
curl -v http://MACHINE_IP/
```

## Solution Walkthrough

**Task 1 - HTTP vs HTTPS**: HTTP runs on port 80 without encryption while HTTPS uses port 443 with TLS encryption. Answer: `HTTP is the protocol used to transfer web pages.`

**Task 2 - Request/Response Structure**: HTTP requests contain method, path, version, headers, and optional body. Responses include status code, headers, and body content.

**Task 3 - HTTP Methods**: GET retrieves data, POST creates data, PUT updates existing data, DELETE removes resources. Answers followed standard REST conventions.

**Task 4 - Status Codes**: Common codes include 200 OK for success, 404 Not Found for missing resources, 500 Internal Server Error for backend issues, and 401 Unauthorized for authentication failures.

**Task 5 - Headers**: Request headers like User-Agent, Host, and Authorization provide metadata. Response headers like Content-Type, Set-Cookie, and Server reveal server details.

**Task 6 - Cookies & Sessions**: Servers set cookies with Set-Cookie header. Browsers send them back with Cookie header to maintain session state across requests.

**Task 7 - Practical**: Started Burp Suite proxy, enabled Intercept, browsed to /room endpoint, forwarded the request, and captured the flag: `THM{YOU'RE_IN_THE_ROOM}`.

## Key Tools Used
- **Burp Suite**: Intercepted and analyzed HTTP traffic
- **curl**: Tested endpoints from terminal
- **Browser DevTools**: Inspected network requests

## Key Learnings
HTTP request/response lifecycle is foundation for web pentesting. Understanding methods, status codes, and headers reveals attack surfaces. Burp Suite proxy workflow becomes second nature.

## Next Steps
Move to DNS in Detail room. HTTP knowledge applies directly to web vulnerability rooms like SQLi, XSS, and CSRF labs.

***