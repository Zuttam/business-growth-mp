# Reddit Research & Thread Discovery

## Prerequisites

Before starting research:
1. Load Reddit engagement strategy from `.business_growth/marketing/social/reddit/strategy.md`
2. Load business context from `.business_growth/marketing/social/BUSINESS.md`
3. If either is missing, create them first (see steps below)

---

## Step 0: Load Reddit Engagement Strategy

```
Read .business_growth/marketing/social/reddit/strategy.md
```

If file doesn't exist, ask the user: **"No Reddit engagement strategy found. Would you like to create one? This defines your overall approach to Reddit — target subreddits, engagement rules, content themes, and goals."**

If user says **yes**, gather the following and create the file:
- **Goal**: What do you want to achieve on Reddit? (brand awareness, traffic, leads, community building)
- **Target Subreddits**: Which subreddits are most relevant?
- **Content Themes**: What topics/expertise should comments and posts focus on?
- **Engagement Rules**: Any constraints? (e.g., never mention product directly, only respond to questions, max posts per day)
- **Tone & Voice**: How should comments sound? (technical expert, friendly peer, industry insider)
- **Metrics to Track**: What signals success? (upvotes, replies, traffic, leads)

Create `.business_growth/marketing/social/reddit/strategy.md` with format:

```markdown
# Reddit Engagement Strategy

## Goal
<what we want to achieve on Reddit>

## Target Subreddits
| Subreddit | Why | Audience | Rules to Note |
|-----------|-----|----------|---------------|
| r/example | <reason> | <who's there> | <key rules> |

## Content Themes
- <theme 1>: <description>
- <theme 2>: <description>

## Engagement Rules
- <rule 1>
- <rule 2>

## Tone & Voice
<description of how comments/posts should sound>

## Metrics & Goals
- <metric>: <target>

## Last Updated: <timestamp>
```

If user says **no**, proceed without a strategy (use business context alone).

---

## Step 1: Load Business Context

```
Read .business_growth/marketing/social/BUSINESS.md
```

If file doesn't exist, proceed to Step 1b. Otherwise, skip to Step 2.

---

## Step 1b: Create Business Context (if missing)

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

Based on the engagement strategy (if available) and business context, determine:
- **Target Subreddits**: Use subreddits from strategy.md if defined, otherwise identify where the target audience discusses relevant topics
- **Search Keywords**: What questions/problems does the audience have?
- **Thread Types**: Questions, discussions, recommendations, complaints
- **Engagement Rules**: Respect any constraints defined in the strategy (e.g., max posts per day, tone requirements)

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
1. Reddit engagement strategy saved in `strategy.md` (if user chose to create one)
2. Business context saved in `BUSINESS.md`
3. Search strategy documented
4. Discovered threads saved to `{YYYY-MM}/{YYYY-MM-DD}.md` with priority rankings
