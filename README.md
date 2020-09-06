# Mojang API Documentation
**A comprehensive list of known and previously undocumented endpoints and payloads**

If you would like to contribute, just make a pull request. If something here is inaccurate, feel free to submit a new issue.

I'm currently looking for someone who has experience with client-side validation of invisible ReCAPTCHAs (v2) in NodeJS. If you're qualified, please get in contact with me!

## Mojang API (api.mojang.com)

### api.mojang.com ###

#### Method: GET ####

Headers: None

Body: None

Response: JSON object with the following fields
```
Status: String - Server status
Runtime-Mode: String - Server runtime mode
Application-Author: String - Application author
Application-Description: String - Application description
Specification-Version: String - Application version
Application-Name: String - Application name
Implementation-Version: String - Application version
Application-Owner: String - Application owner
```

### api.mojang.com/user ###

#### Method: GET ####

Headers:
```
Authorization: Bearer [token]
```
Where `[token]` is a session token generated by a web-authenticated login.

Body: None

Response: JSON object with the following fields
```
id: String - Internal Mojang user ID, not a Minecraft account UUID
emai: String - Email of authenticated user
username: String - Account username, likely email but possibly in-game name
dateOfBirth: Int - Date of birth of authenticated user
secured: Boolean - Whether account has been secured with security questions or not
emailVerified: Boolean - Whether email associated with this account has been verified or not
legacyUser: Boolean - Whether account is a legacy user or not
verifiedByParent: Boolean - Whether account has been verified by parent(s) or not
hashed: Boolean - Whether account data is hashed or not
```

Description: Returns data about current authenticated user

#### Method: POST ####

Headers:
```
Content-Type: application/json
```

Body: JSON object with the following fields
```
source: String - Reason for account creation, "minecraft" by default
emai: String - Email used to create account
repeatEmail: String - Email used to create account
password: String - Password used to create account
day: String - Day component of account creation date
month: String - Month component of account creation date
year: String - Year component of account creation date
date: String - Date of account creation date, with each part seperated by a "-"
g-recaptcha-response: String - ReCAPTCHA response used by Google's ReCAPTCHA API.  Difficult to obtain
suggestedEmail: String - Suggested email if something looks strange about your original input email
dateOfBirth: String - Date of birth of account creator, with each part seperated by a "-"
captcha: String - ReCAPTCHA response used by Google's ReCAPTCHA API.  Difficult to obtain, identical to g-recaptcha-response
languageCode: String - Language code for page translations
```

Response: JSON object with the following fields
```
id: String - Internal Mojang user ID, not a Minecraft account UUID
```

Description: Creates a new Mojang user account

#### Method: PUT ####

Headers:
```
Authorization: Bearer [token]
```
Where `[token]` is a session token generated by a web-authenticated login.

Body: Unknown

Response: Unknown

Description: Likely used to update information about a newly created user
