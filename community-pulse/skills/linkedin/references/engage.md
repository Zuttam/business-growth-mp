# LinkedIn Engagement

## Prerequisites

Before engaging:
1. Business context must exist at `.business_growth/marketing/social/BUSINESS.md`
2. Posts should be discovered and saved to `.business_growth/marketing/social/linkedin/{YYYY-MM}/{YYYY-MM-DD}.md`
3. User must be logged into LinkedIn in the browser (use login skill or log in manually)

---

## Option 1: Comment on Existing Post

### 1.1: Load and Evaluate Posts

```
Read .business_growth/marketing/social/linkedin/{YYYY-MM}/{YYYY-MM-DD}.md
```

If today's file doesn't exist, check previous days or run Research first.

Evaluate post fit based on:
- **Recency**: Is the post still getting engagement? (< 24h ideal, < 3d acceptable)
- **Engagement**: Are people still commenting?
- **Relevance**: Can we provide genuine value?
- **Author**: Is this someone worth building a relationship with?

### 1.2: Draft Proposed Comment

Craft a comment that:
- Leads with insight, not agreement
- Provides a unique perspective or first-hand experience
- Asks a thoughtful follow-up question
- Is professional yet conversational in tone
- Is NOT salesy or promotional
- Mentions product/service ONLY if directly relevant and helpful
- Is under 3 short paragraphs

### 1.3: ASK USER FOR APPROVAL

**CRITICAL**: Present to user:
```
Post Author: <name>
Post Snippet: <first 1-2 lines>
URL: <url>
Post Context: <brief summary of what the post discusses>

Proposed Comment:
---
<drafted comment>
---

Should I post this comment? (yes/no)
```

**Wait for explicit "yes" before proceeding.**

### 1.4: Post Comment via Browser MCP

Upon approval:
```
navigate (post URL) → read_page (verify post) →
find ("comment box" or "Add a comment") → computer (left_click) →
computer (type: comment text) →
find ("Post" or submit button) → computer (left_click) → screenshot (verify posted)
```

### 1.5: Log Engagement

Update today's file at `.business_growth/marketing/social/linkedin/{YYYY-MM}/{YYYY-MM-DD}.md`, appending to the `## Engagement Log` section:

```markdown
### HH:MM - Comment
- **Post Author**: <name>
- **Post Snippet**: <first line>
- **URL**: <url>
- **Content**:
> <comment text>
- **Status**: posted
- **Notes**: <any observations>

---
```

Also update the post's status in the Discovered Posts table to "engaged".

---

## Option 2: Create New Post

### 2.1: Determine Post Strategy

Based on business context, decide:
- **Post type**: Text post, article, poll, or document/carousel
- **Goal**: Thought leadership, question to audience, sharing insight/data, announcing something
- **Target audience**: Who should see and engage with this?

### 2.2: Draft Post

Create a post that:
- Hooks in the first line (pattern interrupt)
- Uses line breaks for readability
- Provides genuine value (insight, data, story, question)
- Includes a CTA or question at the end to drive comments
- Uses 3-5 relevant hashtags
- Is NOT overtly promotional

### 2.3: ASK USER FOR APPROVAL

**CRITICAL**: Present to user:
```
Post Type: <text/article/poll>

Post Content:
---
<drafted post content>
---

Hashtags: #tag1 #tag2 #tag3

Should I publish this post? (yes/no)
```

**Wait for explicit "yes" before proceeding.**

### 2.4: Create Post via Browser MCP

Upon approval:
```
navigate (https://www.linkedin.com/feed/) →
find ("Start a post" button) → computer (left_click) →
computer (type: post content) →
find ("Post" button) → computer (left_click) → screenshot (verify posted)
```

### 2.5: Log Engagement

Update today's file at `.business_growth/marketing/social/linkedin/{YYYY-MM}/{YYYY-MM-DD}.md`, appending to the `## Engagement Log` section:

```markdown
### HH:MM - Post
- **Type**: <text/article/poll>
- **Content**:
> <post text>
- **Hashtags**: #tag1 #tag2 #tag3
- **Status**: posted
- **Notes**: <any observations>

---
```

---

## Best Practices for Engaging LinkedIn Content

### Comments
- Lead with insight, not agreement ("Great post!" adds no value)
- Ask a follow-up question that extends the conversation
- Reference personal experience or specific data points
- Tag relevant people sparingly (only when genuinely additive)
- Keep under 3 short paragraphs
- Reply to other commenters to build visibility in the thread

### Posts
- Hook in the first line (pattern interrupt that stops the scroll)
- Use line breaks for readability (avoid walls of text)
- Include a CTA or question at the end to drive replies
- Use 3-5 relevant hashtags (place at the end)
- Share personal stories and real data over generic advice
- Carousel/document posts get higher reach than plain text
- Best posting times: Tuesday-Thursday mornings (8-10am in your audience's timezone)
- Engage with every comment on your post within the first 2 hours

### General
- Consistency beats virality - post regularly
- Engage with others' content more than you post your own
- Build relationships before asking for anything
- Your profile is your landing page - keep it updated

---

## Engagement Philosophy

### Do's
- Provide genuine value in every interaction
- Share insights that demonstrate professional expertise
- Be transparent about who you are and your affiliations
- Build authentic relationships through consistent engagement
- Respect professional norms and boundaries

### Don'ts
- Never spam connection requests
- Don't engage in posts where your input isn't genuinely relevant
- Avoid generic comments - be specific and thoughtful
- Don't use LinkedIn as a sales pitch channel
- Never create fake profiles or engage in astroturfing
- Don't mass-message connections with promotional content
