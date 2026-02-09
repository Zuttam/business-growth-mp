# Hacker News Research & Thread Discovery

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

## Step 2: Generate HN Search Strategy

Based on business context, determine:
- **Search Keywords**: What technical topics, problems, or questions relate to the business?
- **Thread Types**: Stories, Ask HN, Show HN, comments
- **Sections to Monitor**: Front page, new, ask, show, best

---

## Step 3: Navigate Hacker News via Browser MCP

```
tabs_context_mcp → tabs_create_mcp → navigate (https://news.ycombinator.com)
```

Search across multiple HN sources:

### 3a: Front Page & New
- Navigate to `https://news.ycombinator.com` (front page)
- Navigate to `https://news.ycombinator.com/newest` (new stories)
- Scan titles for relevant topics

### 3b: Algolia Search (keyword-based)
For each search keyword:
- Navigate to `https://hn.algolia.com/?q=<keyword>`
- Filter by date range (last 24h, last week, last month)
- Sort by date or popularity

### 3c: Ask HN
- Navigate to `https://news.ycombinator.com/ask`
- Look for questions related to the business domain

### 3d: Show HN
- Navigate to `https://news.ycombinator.com/show`
- Look for products/projects in the same space (competitors, complementary tools)

---

## Step 4: Extract Thread Data

For each relevant thread found:
- **Title**: Thread title
- **URL**: Full HN thread URL (e.g., `https://news.ycombinator.com/item?id=...`)
- **Points**: Number of upvotes
- **Comments**: Number of comments
- **Age**: How old is the thread
- **Type**: story | ask | show | comment
- **Relevance**: Why this thread is relevant (brief note)
- **Status**: new | evaluated | engaged | skipped

Use `read_page`, `get_page_text`, and `screenshot` to capture thread information.

---

## Step 5: Save to Date-Based Storage

Determine today's date and create the storage path:
```
mkdir -p .business_growth/marketing/social/hackernews/{YYYY-MM}
```

Create/update `.business_growth/marketing/social/hackernews/{YYYY-MM}/{YYYY-MM-DD}.md`:

```markdown
# Hacker News Activity - {YYYY-MM-DD}

## Search Strategy
- **Keywords**: keyword1, keyword2, keyword3
- **Sections Searched**: front page, new, ask, show, algolia
- **Search Time**: HH:MM

## Discovered Threads

### High Priority
| Time | Title | Type | URL | Points | Comments | Age | Relevance | Status |
|------|-------|------|-----|--------|----------|-----|-----------|--------|
| HH:MM | Thread title | story | https://... | 120 | 45 | 2h | Asking about X | new |

### Medium Priority
| Time | Title | Type | URL | Points | Comments | Age | Relevance | Status |
|------|-------|------|-----|--------|----------|-----|-----------|--------|

### Low Priority / Archive
| Time | Title | Type | URL | Points | Comments | Age | Relevance | Status |
|------|-------|------|-----|--------|----------|-----|-----------|--------|

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
