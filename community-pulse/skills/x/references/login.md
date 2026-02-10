# X Login

## Prerequisites

1. Credentials must be saved in `community-pulse/skills/x/.env.profiles.local` (see `.env.profiles.local.template` for format)
2. Browser MCP must be available

---

## Step 0: Load Credentials

```
Read community-pulse/skills/x/.env.profiles.local
```

Parse the INI-style file. Use the `[default]` profile unless the user specifies a different profile name.

If the file doesn't exist, tell the user:
> Copy `.env.profiles.local.template` to `.env.profiles.local` and fill in your X credentials.

---

## Step 1: Ask User for Permission

**CRITICAL**: Before logging in, present to the user:

```
I'm ready to log into X with the following account:
- Profile: <profile name>
- Username: <username>

Should I proceed with the login? (yes/no)
```

**Wait for explicit "yes" before proceeding.**

---

## Step 2: Navigate to X Login

```
tabs_context_mcp → tabs_create_mcp → navigate (https://x.com/login)
```

Take a screenshot to verify the login page loaded.

---

## Step 3: Fill Login Form

X uses a multi-step login flow:

### Step 3a: Enter Username
```
find ("username" or "phone, email, or username" input field) → form_input (username)
find ("Next" button) → computer (left_click)
```

Wait 2-3 seconds for the next step to load.

### Step 3b: Enter Password
```
find ("password" input field) → form_input (password)
```

Take a screenshot to verify fields are filled (password will be masked).

---

## Step 4: Submit Login

```
find ("Log in" button) → computer (left_click)
```

Wait 3-5 seconds for the page to process.

---

## Step 5: Handle Login Results

Take a screenshot and evaluate:

### Success
- Page redirects to x.com/home or the main timeline
- Profile icon appears in the left sidebar
- Report: "Successfully logged in as <username>"

### 2FA Required
- If a 2FA/MFA prompt appears (authenticator app, SMS code), tell the user:
  > X is asking for two-factor authentication. Please complete the 2FA step manually in the browser, then let me know when you're done.
- Wait for user confirmation before continuing

### Phone/Email Verification
- If X asks to verify via phone number or email:
  > X is requesting identity verification. Please complete the verification step manually in the browser, then let me know when you're done.
- Wait for user confirmation before continuing

### Wrong Credentials
- If "Wrong password" or similar error appears:
  > Login failed: incorrect credentials. Please check your `.env.profiles.local` file and try again.

### Rate Limited
- If "Too many attempts" or rate limit message appears:
  > X is rate-limiting login attempts. Please wait a few minutes and try again.

### CAPTCHA / Challenge
- If a CAPTCHA or security challenge appears:
  > X is showing a security challenge. Please complete it manually in the browser, then let me know when you're done.
- Wait for user confirmation before continuing

### Unusual Activity Prompt
- If X shows an "unusual login activity" screen:
  > X has flagged unusual login activity. Please complete the verification step manually in the browser, then let me know when you're done.
- Wait for user confirmation before continuing

---

## Step 6: Verify Login

Navigate to `https://x.com/home` and take a screenshot. Confirm the profile icon is visible in the sidebar, indicating a successful session.
