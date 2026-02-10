# LinkedIn Login

## Prerequisites

1. Credentials must be saved in `community-pulse/skills/linkedin/.env.profiles.local` (see `.env.profiles.local.template` for format)
2. Browser MCP must be available

---

## Step 0: Load Credentials

```
Read community-pulse/skills/linkedin/.env.profiles.local
```

Parse the INI-style file. Use the `[default]` profile unless the user specifies a different profile name.

If the file doesn't exist, tell the user:
> Copy `.env.profiles.local.template` to `.env.profiles.local` and fill in your LinkedIn credentials.

---

## Step 1: Ask User for Permission

**CRITICAL**: Before logging in, present to the user:

```
I'm ready to log into LinkedIn with the following account:
- Profile: <profile name>
- Email: <email>

Should I proceed with the login? (yes/no)
```

**Wait for explicit "yes" before proceeding.**

---

## Step 2: Navigate to LinkedIn Login

```
tabs_context_mcp → tabs_create_mcp → navigate (https://www.linkedin.com/login)
```

Take a screenshot to verify the login page loaded.

---

## Step 3: Fill Login Form

```
find ("email" or "username" input field) → form_input (email)
find ("password" input field) → form_input (password)
```

Take a screenshot to verify fields are filled (password will be masked).

---

## Step 4: Submit Login

```
find ("Sign in" button) → computer (left_click)
```

Wait 3-5 seconds for the page to process.

---

## Step 5: Handle Login Results

Take a screenshot and evaluate:

### Success
- Page redirects to linkedin.com/feed or homepage
- Profile icon/photo appears in the top navigation bar
- Report: "Successfully logged in as <email>"

### 2FA Required
- If a 2FA/MFA prompt appears (email code, authenticator app, SMS), tell the user:
  > LinkedIn is asking for two-factor authentication. Please complete the 2FA step manually in the browser, then let me know when you're done.
- Wait for user confirmation before continuing

### Wrong Credentials
- If "Wrong email or password" or similar error appears:
  > Login failed: incorrect credentials. Please check your `.env.profiles.local` file and try again.

### Rate Limited
- If "Too many attempts" or rate limit message appears:
  > LinkedIn is rate-limiting login attempts. Please wait a few minutes and try again.

### CAPTCHA / Verification Challenge
- If a CAPTCHA or security verification challenge appears:
  > LinkedIn is showing a security verification challenge. Please complete it manually in the browser, then let me know when you're done.
- Wait for user confirmation before continuing

### Phone/Email Verification
- If LinkedIn asks to verify identity via phone or email:
  > LinkedIn is requesting identity verification. Please complete the verification step manually in the browser, then let me know when you're done.
- Wait for user confirmation before continuing

---

## Step 6: Verify Login

Navigate to `https://www.linkedin.com/feed/` and take a screenshot. Confirm the profile icon is visible in the top navigation bar, indicating a successful session.
