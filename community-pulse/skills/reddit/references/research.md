# Reddit Research & Thread Discovery

## Prerequisites

Before starting research:
1. Load business context from `.business_growth/marketing/social/BUSINESS.md`
2. If missing, create it first (see Step 1 below)

---

## Step 0: Load Business Context

```
Read .business_growth/marketing/social/BUSINESS.md
```

If file doesn't exist, proceed to Step 1. Otherwise, skip to Step 2.

---

## Step 1: Create Business Context (if missing)

Ask user for:
- Product/service description
- Company name and website
- Target audience and their pain points
- Value proposition and differentiators
- Tone and messaging guidelines

Create `.business_growth/marketing/social/BUSINESS.md` with format:

```markdown
# Business Profile for Social Marketing

## Business Overview
- **Product/Service**: <description>
- **Company Name**: <name>
- **Website**: <url>

## Target Audience
- **Primary Persona**: <description>
- **Pain Points**: <list>
- **Where They Hang Out**: <platforms/communities>

## Value Proposition
- **Main Value**: <description>
- **Key Differentiators**: <list>

## Messaging Guidelines
- **Tone**: <professional/casual/technical/etc.>
- **Topics to Promote**: <list>
- **Topics to Avoid**: <list>

## Last Updated: <timestamp>
```

---

## Step 2: Generate Reddit Search Strategy

Based on business context, determine:
- **Target Subreddits**: Where does the target audience discuss relevant topics?
- **Search Keywords**: What questions/problems does the audience have?
- **Thread Types**: Questions, discussions, recommendations, complaints

---

## Step 3: Navigate Reddit via Browser MCP

```
tabs_context_mcp → tabs_create_mcp → navigate (reddit.com)
```

For each target subreddit:
1. Navigate to subreddit
2. Search using keywords
3. Sort by "New" or "Hot" depending on strategy
4. Scroll to load more results

---

## Step 4: Extract Thread Data

For each relevant thread found:
- **Title**: Thread title
- **URL**: Full thread URL
- **Subreddit**: r/subredditname
- **Comments**: Number of comments
- **Age**: How old is the thread
- **Relevance**: Why this thread is relevant (brief note)
- **Status**: new | evaluated | engaged | skipped

Use `read_page` and `screenshot` to capture thread information.

---

## Step 5: Save to Date-Based Storage

Determine today's date and create the storage path:
```
mkdir -p .business_growth/marketing/social/reddit/{YYYY-MM}
```

Create/update `.business_growth/marketing/social/reddit/{YYYY-MM}/{YYYY-MM-DD}.md`:

```markdown
# Reddit Activity - {YYYY-MM-DD}

## Search Strategy
- **Target Subreddits**: r/sub1, r/sub2, r/sub3
- **Keywords**: keyword1, keyword2, keyword3
- **Search Time**: HH:MM

## Discovered Threads

### High Priority
| Time | Title | Subreddit | URL | Comments | Age | Relevance | Status |
|------|-------|-----------|-----|----------|-----|-----------|--------|
| HH:MM | Thread title | r/example | https://... | 45 | 2h | Asking about X | new |

### Medium Priority
| Time | Title | Subreddit | URL | Comments | Age | Relevance | Status |
|------|-------|-----------|-----|----------|-----|-----------|--------|

### Low Priority / Archive
| Time | Title | Subreddit | URL | Comments | Age | Relevance | Status |
|------|-------|-----------|-----|----------|-----|-----------|--------|

## Engagement Log

(Entries added by engage.md)
```

If the file already exists for today, append new threads to the appropriate priority sections without overwriting existing entries.

---

## Output

After completing research, you should have:
1. Business context saved in `BUSINESS.md`
2. Search strategy documented
3. Discovered threads saved to `{YYYY-MM}/{YYYY-MM-DD}.md` with priority rankings
