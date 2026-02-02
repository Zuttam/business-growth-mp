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

## Step 5: Save to Threads Database

Create/update `.business_growth/marketing/social/reddit/threads.md`:

```markdown
# Reddit Thread Database

## Search Strategy
- **Target Subreddits**: r/sub1, r/sub2, r/sub3
- **Keywords**: keyword1, keyword2, keyword3
- **Last Search**: <timestamp>

## Discovered Threads

### High Priority
| Title | Subreddit | URL | Comments | Age | Relevance | Status |
|-------|-----------|-----|----------|-----|-----------|--------|
| Thread title | r/example | https://... | 45 | 2h | Asking about X | new |

### Medium Priority
| Title | Subreddit | URL | Comments | Age | Relevance | Status |
|-------|-----------|-----|----------|-----|-----------|--------|

### Low Priority / Archive
| Title | Subreddit | URL | Comments | Age | Relevance | Status |
|-------|-----------|-----|----------|-----|-----------|--------|

### Engaged Threads
| Title | Subreddit | Date Engaged | Type | URL |
|-------|-----------|--------------|------|-----|
```

---

## Output

After completing research, you should have:
1. Business context saved in `BUSINESS.md`
2. Search strategy documented
3. Discovered threads saved to `threads.md` with priority rankings
