# Instagram Research & Content Discovery

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

## Step 2: Generate Instagram Search Strategy

Based on business context, determine:
- **Target Hashtags**: What hashtags does the audience use? (e.g., #startup, #saas, #buildinpublic, #growthhacking, #entrepreneurlife)
- **Target Accounts**: Who are competitors, influencers, and thought leaders on Instagram?
- **Search Keywords**: What topics does the audience discuss in captions and comments?
- **Content Types to Monitor**: Image posts, carousel posts, Reels

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
1. Business context saved in `BUSINESS.md`
2. Search strategy documented
3. Discovered posts saved to `{YYYY-MM}/{YYYY-MM-DD}.md` with priority rankings
4. Accounts to follow identified and logged
