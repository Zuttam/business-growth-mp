---
name: reddit
description: Reddit community engagement and marketing. Use when user wants to: (a) Find relevant Reddit threads for their business; (b) Engage with Reddit communities (comment, post); (c) Discover subreddits where their audience hangs out; (d) Track Reddit engagement history; (e) Research Reddit marketing opportunities.
---

# Reddit Community Engagement Skill

## Overview

This skill enables authentic Reddit engagement by discovering relevant threads, crafting helpful responses, and tracking engagement history.

## Actions

| Action | File | When to Use |
|--------|------|-------------|
| **Login** | [references/login.md](./references/login.md) | Authenticate with Reddit before engaging |
| **Research** | [references/research.md](./references/research.md) | Find threads, discover subreddits, build thread database |
| **Engage** | [references/engage.md](./references/engage.md) | Comment on threads, create new posts, or check notifications |

## Data Files

| File | Purpose |
|------|---------|
| `.business_growth/marketing/social/BUSINESS.md` | Shared business context (required) |
| `.business_growth/marketing/social/reddit/{YYYY-MM}/{YYYY-MM-DD}.md` | Daily threads and engagement log |
| `community-pulse/skills/reddit/.env.profiles.local` | Reddit credentials (gitignored) |

## Quick Start

1. **First time?** → Run **Login** to authenticate, then **Research** to find threads
2. **Have threads?** → Run **Engage** to comment or post

## Decision Flow

```
User Request
    │
    ├─► "Login" / "Sign in" / "Authenticate"
    │       └─► Load references/login.md
    │
    ├─► "Find threads" / "Research" / "Discover"
    │       └─► Load references/research.md
    │
    ├─► "Comment" / "Post" / "Engage" / "Reply"
    │       └─► Load references/engage.md
    │
    ├─► "Check notifications" / "Check replies" / "Follow up"
    │       └─► Load references/engage.md (Option 3)
    │
    ├─► "Execute today's strategy" / "Run daily strategy"
    │       └─► Load references/engage.md (Option 3 first, then Option 1)
    │
    └─► Unclear
            └─► Ask: "Would you like me to research new threads or engage with existing ones?"
```

---

## Browser MCP Quick Reference

### Get Browser Context
```
tabs_context_mcp (get available tabs)
tabs_create_mcp (create new tab if needed)
```

### Navigation
```
navigate (url, tabId)
```

### Reading Page
```
read_page (tabId) - Get page structure
get_page_text (tabId) - Get text content
screenshot - Visual verification
```

### Finding Elements
```
find (query, tabId) - Natural language element search
```

### Interaction
```
form_input (ref, value, tabId) - Fill form fields
computer (action: "left_click", coordinate, tabId) - Click elements
computer (action: "scroll", scroll_direction, tabId) - Scroll page
computer (action: "type", text, tabId) - Type text
```

---

## Important Notes

1. **Authentication**: Use login skill or ensure manual login before engaging
2. **Rate Limits**: Reddit limits posting frequency - wait between actions
3. **Karma Requirements**: Some subreddits require minimum karma to post
4. **Shadowbans**: Aggressive posting can trigger Reddit's spam detection
5. **Authenticity**: Focus on providing value, not promotion
6. **User Approval**: ALL engagement actions require explicit user confirmation
