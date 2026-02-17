---
name: instagram
description: Instagram community engagement and marketing. Use when user wants to: (a) Find relevant Instagram posts and accounts in their niche; (b) Engage with Instagram content (comment, follow); (c) Discover hashtags, influencers, and accounts to engage with; (d) Track Instagram engagement history; (e) Research Instagram marketing opportunities.
---

# Instagram Community Engagement Skill

## Overview

This skill enables authentic Instagram engagement by discovering relevant posts and accounts, crafting thoughtful comments, and tracking engagement history.

## Actions

| Action | File | When to Use |
|--------|------|-------------|
| **Login** | [references/login.md](./references/login.md) | Authenticate with Instagram before engaging |
| **Research** | [references/research.md](./references/research.md) | Find posts, discover accounts/hashtags, build content database |
| **Engage** | [references/engage.md](./references/engage.md) | Comment on posts, follow accounts, or reply to comments |

## Data Files

| File | Purpose |
|------|---------|
| `.business_growth/marketing/social/BUSINESS.md` | Shared business context (required) |
| `.business_growth/marketing/social/instagram/{YYYY-MM}/{YYYY-MM-DD}.md` | Daily posts, accounts, and engagement log |
| `community-pulse/skills/instagram/.env.profiles.local` | Instagram credentials (gitignored) |

## Quick Start

1. **First time?** → Run **Login** to authenticate, then **Research** to find posts
2. **Have posts?** → Run **Engage** to comment or follow

## Decision Flow

```
User Request
    │
    ├─► "Login" / "Sign in" / "Authenticate"
    │       └─► Load references/login.md
    │
    ├─► "Find posts" / "Research" / "Discover" / "Find accounts" / "Find hashtags"
    │       └─► Load references/research.md
    │
    ├─► "Comment" / "Follow" / "Engage" / "Reply"
    │       └─► Load references/engage.md
    │
    ├─► "Check replies" / "Follow up"
    │       └─► Load references/engage.md (Option 3)
    │
    ├─► "Execute today's strategy" / "Run daily strategy"
    │       └─► Load references/engage.md (Option 3 first, then Option 1)
    │
    └─► Unclear
            └─► Ask: "Would you like me to research Instagram posts/accounts or engage with existing content?"
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
2. **Rate Limits**: Instagram aggressively limits actions (comments, follows) - wait between actions to avoid temporary blocks
3. **Visual Platform**: Instagram is image/video-first; comments and follows are the primary text-based engagement opportunities
4. **Hashtag Strategy**: Use relevant hashtags when discovering content; Instagram discovery is hashtag-driven
5. **Action Blocks**: Rapid commenting or following can trigger temporary action blocks (24-48h)
6. **User Approval**: ALL engagement actions require explicit user confirmation
