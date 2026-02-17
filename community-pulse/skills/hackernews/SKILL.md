---
name: hackernews
description: |
  Hacker News community engagement and marketing. Use when user wants to:
  - Find relevant Hacker News discussions for their business
  - Engage with HN communities (comment, submit posts)
  - Discover trending topics and discussions on HN
  - Track Hacker News engagement history
  - Research HN marketing opportunities
  - Post to Ask HN or Show HN
---

# Hacker News Community Engagement Skill

## Overview

This skill enables authentic Hacker News engagement by discovering relevant discussions, crafting thoughtful responses, and tracking engagement history.

## Actions

| Action | File | When to Use |
|--------|------|-------------|
| **Login** | [references/login.md](./references/login.md) | Authenticate with HN before engaging |
| **Research** | [references/research.md](./references/research.md) | Find discussions, search topics, build thread database |
| **Engage** | [references/engage.md](./references/engage.md) | Comment on discussions or submit new posts |

## Data Files

| File | Purpose |
|------|---------|
| `.business_growth/marketing/social/BUSINESS.md` | Shared business context (required) |
| `.business_growth/marketing/social/hackernews/strategy.md` | Hacker News engagement strategy (overall approach, topics, expertise areas) |
| `.business_growth/marketing/social/hackernews/{YYYY-MM}/{YYYY-MM-DD}.md` | Daily threads and engagement log |
| `community-pulse/skills/hackernews/.env.profiles.local` | HN credentials (gitignored) |

## Quick Start

1. **First time?** → Run **Login** to authenticate, then **Research** to find discussions
2. **Have threads?** → Run **Engage** to comment or submit posts
3. **Before any Research or Engagement** → The strategy file at `.business_growth/marketing/social/hackernews/strategy.md` is loaded automatically. If it doesn't exist, you'll be asked if you want to create one.

## Decision Flow

```
User Request
    │
    ├─► "Login" / "Sign in" / "Authenticate"
    │       └─► Load references/login.md
    │
    ├─► "Find threads" / "Research" / "Discover" / "Search HN"
    │       └─► Load references/research.md
    │
    ├─► "Comment" / "Post" / "Submit" / "Engage" / "Reply"
    │       └─► Load references/engage.md
    │
    └─► Unclear
            └─► Ask: "Would you like me to research HN discussions or engage with existing ones?"
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
2. **Karma Requirements**: New accounts have limited posting ability; commenting builds karma
3. **Rate Limits**: HN limits posting frequency - wait between submissions
4. **Culture**: HN values substance, intellectual curiosity, and technical depth
5. **Showdead**: Flagged/dead comments are hidden - avoid promotional or low-quality content
6. **User Approval**: ALL engagement actions require explicit user confirmation
