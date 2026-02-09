# Reddit Login

## Prerequisites

1. Credentials must be saved in `community-pulse/skills/reddit/.env.profiles.local` (see `.env.profiles.local.template` for format)
2. Browser MCP must be available

---

## Step 0: Load Credentials

```
Read community-pulse/skills/reddit/.env.profiles.local
```

Parse the INI-style file. Use the `[default]` profile unless the user specifies a different profile name.

If the file doesn't exist, tell the user:
> Copy `.env.profiles.local.template` to `.env.profiles.local` and fill in your Reddit credentials.

---

## Step 1: Ask User for Permission

**CRITICAL**: Before logging in, present to the user:

```
I'm ready to log into Reddit with the following account:
- Profile: <profile name>
- Username: <username>

Should I proceed with the login? (yes/no)
```

**Wait for explicit "yes" before proceeding.**

---

## Step 2: Navigate to Reddit Login

```
tabs_context_mcp → tabs_create_mcp → navigate (https://www.reddit.com/login)
```

Take a screenshot to verify the login page loaded.

---

## Step 3: Fill Login Form

```
find ("username" input field) → form_input (username)
find ("password" input field) → form_input (password)
```

Take a screenshot to verify fields are filled (password will be masked).

---

## Step 4: Submit Login

```
find ("Log In" or "Sign In" button) → computer (left_click)
```

Wait 3-5 seconds for the page to process.

---

## Step 5: Handle Login Results

Take a screenshot and evaluate:

### Success
- Page redirects to reddit.com homepage or feed
- Username appears in the top-right corner
- Report: "Successfully logged in as <username>"

### 2FA Required
- If a 2FA/MFA prompt appears, tell the user:
  > Reddit is asking for two-factor authentication. Please complete the 2FA step manually in the browser, then let me know when you're done.
- Wait for user confirmation before continuing

### Wrong Credentials
- If "Incorrect username or password" or similar error appears:
  > Login failed: incorrect credentials. Please check your `.env.profiles.local` file and try again.

### Rate Limited
- If "Too many attempts" or rate limit message appears:
  > Reddit is rate-limiting login attempts. Please wait a few minutes and try again.

### CAPTCHA
- If a CAPTCHA challenge appears:
  > Reddit is showing a CAPTCHA. Please complete it manually in the browser, then let me know when you're done.
- Wait for user confirmation before continuing

---

## Step 6: Verify Login

Navigate to `https://www.reddit.com` and take a screenshot. Confirm the username is visible in the UI, indicating a successful session.
