---
name: linkedin
description: |
  LinkedIn community engagement and marketing. Use when user wants to:
  - Find relevant LinkedIn posts and discussions
  - Discover people and thought leaders to follow
  - Engage with LinkedIn content (comment, post)
  - Track LinkedIn engagement history
  - Research LinkedIn marketing opportunities
---

# LinkedIn Community Engagement Skill

## Overview

This skill enables authentic LinkedIn engagement by discovering relevant posts, identifying thought leaders to follow, crafting professional responses, and tracking engagement history.

## Actions

| Action | File | When to Use |
|--------|------|-------------|
| **Login** | [references/login.md](./references/login.md) | Authenticate with LinkedIn before engaging |
| **Research** | [references/research.md](./references/research.md) | Find posts, discover people, build content database |
| **Engage** | [references/engage.md](./references/engage.md) | Comment on posts or create new posts |

## Data Files

| File | Purpose |
|------|---------|
| `.business_growth/marketing/social/BUSINESS.md` | Shared business context (required) |
| `.business_growth/marketing/social/linkedin/strategy.md` | LinkedIn engagement strategy (overall approach, target audiences, content pillars) |
| `.business_growth/marketing/social/linkedin/{YYYY-MM}/{YYYY-MM-DD}.md` | Daily posts, people, and engagement log |
| `community-pulse/skills/linkedin/.env.profiles.local` | LinkedIn credentials (gitignored) |

## Quick Start

1. **First time?** → Run **Login** to authenticate, then **Research** to find posts and people
2. **Have posts?** → Run **Engage** to comment or create new posts
3. **Before any Research or Engagement** → The strategy file at `.business_growth/marketing/social/linkedin/strategy.md` is loaded automatically. If it doesn't exist, you'll be asked if you want to create one.

## Decision Flow

```
User Request
    │
    ├─► "Login" / "Sign in" / "Authenticate"
    │       └─► Load references/login.md
    │
    ├─► "Find posts" / "Research" / "Discover" / "Find people"
    │       └─► Load references/research.md
    │
    ├─► "Comment" / "Post" / "Engage" / "Reply"
    │       └─► Load references/engage.md
    │
    └─► Unclear
            └─► Ask: "Would you like me to research LinkedIn posts/people or engage with existing content?"
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
2. **Rate Limits**: LinkedIn limits connection requests and posting frequency
3. **Professional Tone**: LinkedIn rewards professional, insightful content
4. **Connection Limits**: Avoid mass connection requests - focus on quality engagement
5. **Content Visibility**: LinkedIn algorithm favors comments and engagement within the first hour
6. **User Approval**: ALL engagement actions require explicit user confirmation
