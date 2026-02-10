---
name: x
description: |
  X (Twitter) community engagement and marketing. Use when user wants to:
  - Find relevant tweets and threads
  - Discover people and thought leaders to follow
  - Engage with X content (reply, post, quote tweet)
  - Track X engagement history
  - Research X marketing opportunities
---

# X Community Engagement Skill

## Overview

This skill enables authentic X engagement by discovering relevant tweets and threads, identifying thought leaders to follow, crafting concise replies and posts, and tracking engagement history.

## Actions

| Action | File | When to Use |
|--------|------|-------------|
| **Login** | [references/login.md](./references/login.md) | Authenticate with X before engaging |
| **Research** | [references/research.md](./references/research.md) | Find tweets, discover people, build content database |
| **Engage** | [references/engage.md](./references/engage.md) | Reply to tweets, create new tweets, or quote tweet |

## Data Files

| File | Purpose |
|------|---------|
| `.business_growth/marketing/social/BUSINESS.md` | Shared business context (required) |
| `.business_growth/marketing/social/x/{YYYY-MM}/{YYYY-MM-DD}.md` | Daily tweets, people, and engagement log |
| `community-pulse/skills/x/.env.profiles.local` | X credentials (gitignored) |

## Quick Start

1. **First time?** → Run **Login** to authenticate, then **Research** to find tweets and people
2. **Have tweets?** → Run **Engage** to reply, post, or quote tweet

## Decision Flow

```
User Request
    │
    ├─► "Login" / "Sign in" / "Authenticate"
    │       └─► Load references/login.md
    │
    ├─► "Find tweets" / "Research" / "Discover" / "Find people"
    │       └─► Load references/research.md
    │
    ├─► "Reply" / "Tweet" / "Post" / "Engage" / "Quote"
    │       └─► Load references/engage.md
    │
    └─► Unclear
            └─► Ask: "Would you like me to research X posts/people or engage with existing content?"
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
2. **Rate Limits**: X limits tweet frequency and API access - wait between actions
3. **Character Limit**: Tweets are limited to 280 characters (threads for longer content)
4. **Shadowbans**: Aggressive tweeting or follow/unfollow can trigger restrictions
5. **Algorithm**: X algorithm favors engagement (replies, quotes) over plain tweets
6. **User Approval**: ALL engagement actions require explicit user confirmation
