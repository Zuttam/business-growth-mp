# Hacker News Login

## Prerequisites

1. Credentials must be saved in `community-pulse/skills/hackernews/.env.profiles.local` (see `.env.profiles.local.template` for format)
2. Browser MCP must be available

---

## Step 0: Load Credentials

```
Read community-pulse/skills/hackernews/.env.profiles.local
```

Parse the INI-style file. Use the `[default]` profile unless the user specifies a different profile name.

If the file doesn't exist, tell the user:
> Copy `.env.profiles.local.template` to `.env.profiles.local` and fill in your Hacker News credentials.

---

## Step 1: Ask User for Permission

**CRITICAL**: Before logging in, present to the user:

```
I'm ready to log into Hacker News with the following account:
- Profile: <profile name>
- Username: <username>

Should I proceed with the login? (yes/no)
```

**Wait for explicit "yes" before proceeding.**

---

## Step 2: Navigate to HN Login

```
tabs_context_mcp → tabs_create_mcp → navigate (https://news.ycombinator.com/login)
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
find ("login" button) → computer (left_click)
```

Wait 2-3 seconds for the page to process.

---

## Step 5: Handle Login Results

Take a screenshot and evaluate:

### Success
- Page redirects to news.ycombinator.com front page
- Username appears in the top-right header bar
- Report: "Successfully logged in as <username>"

### Bad Login
- If "Bad login." message appears:
  > Login failed: incorrect credentials. Please check your `.env.profiles.local` file and try again.

### Rate Limited
- If the page shows an error about too many attempts:
  > HN is rate-limiting login attempts. Please wait a few minutes and try again.

### Karma Restrictions
- Note: New accounts may have limited posting ability. If the user encounters restrictions after login, inform them:
  > Your HN account may have limited posting ability due to low karma. Commenting on existing threads builds karma over time.

---

## Step 6: Verify Login

Navigate to `https://news.ycombinator.com` and take a screenshot. Confirm the username is visible in the top navigation bar, indicating a successful session.
