# Instagram Research & Content Discovery

## Prerequisites

Before starting research:
1. Load Instagram engagement strategy from `.business_growth/marketing/social/instagram/strategy.md`
2. Load business context from `.business_growth/marketing/social/BUSINESS.md`
3. If either is missing, create them first (see steps below)

---

## Step 0: Load Instagram Engagement Strategy

```
Read .business_growth/marketing/social/instagram/strategy.md
```

If file doesn't exist, ask the user: **"No Instagram engagement strategy found. Would you like to create one? This defines your overall approach to Instagram — hashtag groups, target accounts, content themes, and goals."**

If user says **yes**, gather the following and create the file:
- **Goal**: What do you want to achieve on Instagram? (brand awareness, community building, traffic, influencer relationships)
- **Target Accounts**: Who are key accounts, influencers, and competitors to engage with?
- **Hashtag Groups**: What hashtag clusters are relevant? (niche hashtags, industry hashtags, community hashtags)
- **Content Themes**: What topics/expertise should comments focus on?
- **Engagement Rules**: Any constraints? (e.g., max comments per day, avoid competitor posts, comment-before-follow strategy)
- **Tone & Voice**: How should comments sound? (friendly peer, helpful expert, enthusiastic supporter)
- **Metrics to Track**: What signals success? (followers, comment replies, profile visits, engagement rate)

Create `.business_growth/marketing/social/instagram/strategy.md` with format:

```markdown
# Instagram Engagement Strategy

## Goal
<what we want to achieve on Instagram>

## Target Accounts
| Account | Why | Followers | Niche |
|---------|-----|-----------|-------|
| @example | <reason> | <count> | <niche> |

## Hashtag Groups
- **Niche**: <hashtags specific to your industry>
- **Community**: <hashtags your audience uses>
- **Discovery**: <broader hashtags for reach>

## Content Themes
- <theme 1>: <description>
- <theme 2>: <description>

## Engagement Rules
- <rule 1>
- <rule 2>

## Tone & Voice
<description of how comments should sound>

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

## Step 2: Generate Instagram Search Strategy

Based on the engagement strategy (if available) and business context, determine:
- **Target Hashtags**: Use hashtag groups from strategy.md if defined, otherwise identify what hashtags the audience uses (e.g., #startup, #saas, #buildinpublic, #growthhacking, #entrepreneurlife)
- **Target Accounts**: Use accounts from strategy.md if defined, otherwise identify competitors, influencers, and thought leaders on Instagram
- **Search Keywords**: What topics does the audience discuss in captions and comments?
- **Content Types to Monitor**: Image posts, carousel posts, Reels
- **Engagement Rules**: Respect any constraints defined in the strategy (e.g., max comments per day, tone requirements)

---

## Step 3: Navigate Instagram via Browser MCP

```
tabs_context_mcp → tabs_create_mcp → navigate (https://www.instagram.com/)
```

Search across multiple Instagram discovery channels:

### 3a: Hashtag Pages (Primary Discovery)
For each target hashtag:
- Navigate to `https://www.instagram.com/explore/tags/<hashtag>/` (without the # symbol)
- Scan "Top" and "Recent" posts
- Use `read_page` and `screenshot` to capture post previews
- Click into individual posts to read full captions and comment counts
- Scroll to load more posts if needed

### 3b: Explore Page
- Navigate to `https://www.instagram.com/explore/`
- Scan the algorithm-curated content for relevant posts
- Scroll to load more content
- Click into posts that appear relevant to the business niche

### 3c: Account Timelines
For known key accounts (competitors, influencers, thought leaders):
- Navigate to `https://www.instagram.com/<username>/`
- Scan recent posts for engagement opportunities
- Note follower counts, post frequency, and engagement levels

### 3d: Search via UI
Instagram search is accessed through the UI rather than URL parameters:
- Find the search icon (magnifying glass) in the navigation
- Click into the search bar
- Type keyword searches
- Browse "Accounts", "Tags", and "Places" tabs in search results
- Explore suggested accounts and hashtags

---

## Step 4: Extract Data

### Posts
For each relevant post found:
- **Author**: Username (@handle)
- **Caption Preview**: First 1-2 lines of the caption
- **URL**: Full post URL (format: `https://www.instagram.com/p/<shortcode>/`)
- **Likes**: Number of likes (if visible)
- **Comments**: Number of comments
- **Type**: Image / Carousel / Reel
- **Age**: How old is the post
- **Relevance**: Why this post is relevant (brief note)
- **Status**: new | evaluated | engaged | skipped

### Accounts to Follow
For each relevant account discovered:
- **Username**: @handle
- **Name**: Display name
- **Bio**: Profile bio
- **URL**: Profile URL (`https://www.instagram.com/<username>/`)
- **Followers**: Follower count
- **Relevance**: Why this account is worth following (brief note)
- **Status**: new | followed | skipped

Use `read_page`, `get_page_text`, and `screenshot` to capture information.

---

## Step 5: Save to Date-Based Storage

Determine today's date and create the storage path:
```
mkdir -p .business_growth/marketing/social/instagram/{YYYY-MM}
```

Create/update `.business_growth/marketing/social/instagram/{YYYY-MM}/{YYYY-MM-DD}.md`:

```markdown
# Instagram Activity - {YYYY-MM-DD}

## Search Strategy
- **Hashtags**: #hashtag1, #hashtag2, #hashtag3
- **Accounts Monitored**: @account1, @account2, @account3
- **Keywords**: keyword1, keyword2, keyword3
- **Search Time**: HH:MM

## Accounts to Follow
| Time | Username | Name | Bio | URL | Followers | Relevance | Status |
|------|----------|------|-----|-----|-----------|-----------|--------|
| HH:MM | @janedoe | Jane Doe | Building SaaS tools | https://instagram.com/janedoe | 12.5K | Industry thought leader | new |

## Discovered Posts

### High Priority
| Time | Author | Caption Preview | URL | Likes | Comments | Type | Age | Relevance | Status |
|------|--------|----------------|-----|-------|----------|------|-----|-----------|--------|
| HH:MM | @johnsmith | How we scaled our... | https://instagram.com/p/... | 1.2K | 89 | Image | 3h | Discusses our target problem | new |

### Medium Priority
| Time | Author | Caption Preview | URL | Likes | Comments | Type | Age | Relevance | Status |
|------|--------|----------------|-----|-------|----------|------|-----|-----------|--------|

### Low Priority / Archive
| Time | Author | Caption Preview | URL | Likes | Comments | Type | Age | Relevance | Status |
|------|--------|----------------|-----|-------|----------|------|-----|-----------|--------|

## Engagement Log

(Entries added by engage.md)
```

If the file already exists for today, append new posts and accounts to the appropriate sections without overwriting existing entries.

---

## What Makes a Good Instagram Engagement Target

Prioritize posts that:
- Have **active comment sections** with ongoing conversation
- Are from **accounts in your target niche** with engaged followers
- Have **text-heavy captions** that invite discussion (questions, opinions, advice)
- Were posted **within the last 12 hours** (Instagram algorithm favors early engagement)
- Are from accounts where **your expertise adds a unique perspective**
- Have a **high comment-to-like ratio** (indicates discussion, not just passive scrolling)
- Use **relevant hashtags** that your target audience follows
- Are **carousel posts or Reels** (these tend to have higher engagement and longer shelf life)
- Have **fewer than 100 comments** (easier to get visibility in the thread)

---

## Output

After completing research, you should have:
1. Instagram engagement strategy saved in `strategy.md` (if user chose to create one)
2. Business context saved in `BUSINESS.md`
3. Search strategy documented
4. Discovered posts saved to `{YYYY-MM}/{YYYY-MM-DD}.md` with priority rankings
5. Accounts to follow identified and logged
