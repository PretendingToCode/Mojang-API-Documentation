# Mojang-API-Documentation
**A comprehensive list of known and previously undocumented endpoints and payloads**

If you would like to contribute, just make a pull request. If something here is inaccurate, feel free to submit a new issue.

I'm currently looking for someone who has experience with client-side validation of invisible ReCAPTCHAs (v2) in NodeJS. If you're qualified, please get in contact with me!

## Mojang API (api.mojang.com)

**api.mojang.com/**
Request type: GET
Headers: None
Body: None
Response: JSON object containing information about the Mojang API server with the following fields:
```
Status: String
Runtime-Mode: String
Application-Author: String
Application-Description: String
Specification-Version: String
Application-Name: String
Implementation-Version: String
Application-Owner: String
```
