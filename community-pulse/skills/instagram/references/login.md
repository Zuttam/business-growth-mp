# Instagram Login

## Prerequisites

1. Credentials must be saved in `community-pulse/skills/instagram/.env.profiles.local` (see `.env.profiles.local.template` for format)
2. Browser MCP must be available

---

## Step 0: Load Credentials

```
Read community-pulse/skills/instagram/.env.profiles.local
```

Parse the INI-style file. Use the `[default]` profile unless the user specifies a different profile name.

If the file doesn't exist, tell the user:
> Copy `.env.profiles.local.template` to `.env.profiles.local` and fill in your Instagram credentials.

---

## Step 1: Ask User for Permission

**CRITICAL**: Before logging in, present to the user:

```
I'm ready to log into Instagram with the following account:
- Profile: <profile name>
- Username: <username>

Should I proceed with the login? (yes/no)
```

**Wait for explicit "yes" before proceeding.**

---

## Step 2: Navigate to Instagram Login

```
tabs_context_mcp → tabs_create_mcp → navigate (https://www.instagram.com/accounts/login/)
```

Take a screenshot to verify the login page loaded.

---

## Step 3: Fill Login Form

Instagram uses a single-page login form with username and password fields:

```
find ("Phone number, username, or email" input field) → form_input (username)
find ("Password" input field) → form_input (password)
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
- Page redirects to instagram.com feed
- Profile icon or navigation bar appears
- Report: "Successfully logged in as <username>"

### "Save Your Login Info?" Popup
Instagram commonly shows this prompt after login. Dismiss it:
> Instagram is asking to save login info. I'll dismiss this and continue.
```
find ("Not Now" button) → computer (left_click)
```

### "Turn on Notifications?" Popup
Another common Instagram post-login popup. Dismiss it:
> Instagram is asking about notifications. I'll dismiss this and continue.
```
find ("Not Now" button) → computer (left_click)
```

### 2FA Required
- If a 2FA/MFA prompt appears (SMS code or authenticator app), tell the user:
  > Instagram is asking for two-factor authentication. Please complete the 2FA step manually in the browser, then let me know when you're done.
- Wait for user confirmation before continuing

### Wrong Credentials
- If "Sorry, your password was incorrect" or similar error appears:
  > Login failed: incorrect credentials. Please check your `.env.profiles.local` file and try again.

### Rate Limited
- If "Please wait a few minutes before you try again" or similar message appears:
  > Instagram is rate-limiting login attempts. Please wait a few minutes and try again.

### CAPTCHA / Suspicious Login
- If Instagram shows "We Detected An Unusual Login Attempt" or a CAPTCHA challenge:
  > Instagram flagged this as an unusual login. Please complete the verification manually in the browser, then let me know when you're done.
- Wait for user confirmation before continuing

### Account Disabled / Locked
- If Instagram shows an account restriction or disabled notice:
  > Your Instagram account appears to be restricted or disabled. Please check your account status directly on Instagram.

---

## Step 6: Verify Login

Navigate to `https://www.instagram.com/` and take a screenshot. Confirm the profile icon is visible in the navigation, indicating a successful session.
