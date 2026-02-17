# X Engagement

## Prerequisites

Before engaging:
1. Load X engagement strategy from `.business_growth/marketing/social/x/strategy.md` — if it doesn't exist, ask the user: **"No X engagement strategy found. Would you like to create one before engaging?"** If yes, follow the strategy creation flow in [references/research.md](./research.md) Step 0. If no, proceed without it.
2. Business context must exist at `.business_growth/marketing/social/BUSINESS.md`
3. Tweets should be discovered and saved to `.business_growth/marketing/social/x/{YYYY-MM}/{YYYY-MM-DD}.md`
4. User must be logged into X in the browser (use login skill or log in manually)

---

## Option 1: Reply to Existing Tweet

### 1.1: Load and Evaluate Tweets

```
Read .business_growth/marketing/social/x/{YYYY-MM}/{YYYY-MM-DD}.md
```

If today's file doesn't exist, check previous days or run Research first.

Evaluate tweet fit based on:
- **Recency**: Is the tweet still getting engagement? (< 12h ideal, < 48h acceptable)
- **Engagement**: Are people still replying?
- **Relevance**: Can we provide genuine value?
- **Author**: Is this someone worth building a relationship with?

### 1.2: Draft Proposed Reply

Craft a reply that:
- Adds genuine value (not just "great point!")
- Quotes or references a specific part of the tweet
- Shares a contrarian or nuanced take when appropriate
- Is concise and fits within 280 characters
- Is NOT salesy or promotional
- Mentions product/service ONLY if directly relevant and helpful

### 1.3: ASK USER FOR APPROVAL

**CRITICAL**: Present to user:
```
Tweet Author: @<handle>
Tweet Content: <tweet text>
URL: <url>

Proposed Reply:
---
<drafted reply>
---

Character count: <count>/280

Should I post this reply? (yes/no)
```

**Wait for explicit "yes" before proceeding.**

### 1.4: Post Reply via Browser MCP

Upon approval:
```
navigate (tweet URL) → read_page (verify tweet) →
find ("Reply" button or reply input) → computer (left_click) →
computer (type: reply text) →
find ("Reply" or "Post" submit button) → computer (left_click) → screenshot (verify posted)
```

### 1.5: Log Engagement

Update today's file at `.business_growth/marketing/social/x/{YYYY-MM}/{YYYY-MM-DD}.md`, appending to the `## Engagement Log` section:

```markdown
### HH:MM - Reply
- **Tweet Author**: @<handle>
- **Tweet**: <original tweet snippet>
- **URL**: <url>
- **Content**:
> <reply text>
- **Status**: posted
- **Notes**: <any observations>

---
```

Also update the tweet's status in the Discovered Tweets table to "engaged".

---

## Option 2: Create New Tweet

### 2.1: Determine Tweet Strategy

Based on business context, decide:
- **Goal**: Thought leadership, question to audience, sharing insight/data, hot take
- **Format**: Single tweet (280 chars) or thread
- **Target audience**: Who should see and engage with this?

### 2.2: Draft Tweet

Create a tweet that:
- Hooks in the first 7 words
- Fits within 280 characters (or plan as a thread)
- Provides genuine value (insight, data, question, hot take)
- Uses 1-2 hashtags max (X penalizes hashtag stuffing)
- Ends with a question or provocative statement to drive replies
- Is NOT overtly promotional

### 2.3: ASK USER FOR APPROVAL

**CRITICAL**: Present to user:
```
Tweet:
---
<drafted tweet content>
---

Character count: <count>/280

Should I post this tweet? (yes/no)
```

**Wait for explicit "yes" before proceeding.**

### 2.4: Create Tweet via Browser MCP

Upon approval:
```
navigate (https://x.com/home) →
find ("What is happening?!" or compose tweet button) → computer (left_click) →
computer (type: tweet content) →
find ("Post" button) → computer (left_click) → screenshot (verify posted)
```

### 2.5: Log Engagement

Update today's file at `.business_growth/marketing/social/x/{YYYY-MM}/{YYYY-MM-DD}.md`, appending to the `## Engagement Log` section:

```markdown
### HH:MM - Tweet
- **Content**:
> <tweet text>
- **Status**: posted
- **Notes**: <any observations>

---
```

---

## Option 3: Quote Tweet

### 3.1: Load and Select Tweet

```
Read .business_growth/marketing/social/x/{YYYY-MM}/{YYYY-MM-DD}.md
```

Select a tweet worth quote-tweeting (adds your commentary to their content).

### 3.2: Draft Quote Comment

Craft a quote that:
- Adds your own perspective, data, or insight on top of the original
- Is concise (280 chars including any hashtags)
- Amplifies the original tweet while showcasing your expertise
- Is NOT just a restatement of the original

### 3.3: ASK USER FOR APPROVAL

**CRITICAL**: Present to user:
```
Original Tweet by @<handle>: <tweet text>
URL: <url>

Quote Comment:
---
<drafted quote comment>
---

Character count: <count>/280

Should I post this quote tweet? (yes/no)
```

**Wait for explicit "yes" before proceeding.**

### 3.4: Post Quote Tweet via Browser MCP

Upon approval:
```
navigate (tweet URL) → find ("Retweet" or "Repost" button) → computer (left_click) →
find ("Quote" option) → computer (left_click) →
computer (type: quote comment) →
find ("Post" button) → computer (left_click) → screenshot (verify posted)
```

### 3.5: Log Engagement

Update today's file at `.business_growth/marketing/social/x/{YYYY-MM}/{YYYY-MM-DD}.md`, appending to the `## Engagement Log` section:

```markdown
### HH:MM - Quote Tweet
- **Original Author**: @<handle>
- **Original Tweet**: <tweet snippet>
- **URL**: <url>
- **Quote Comment**:
> <quote text>
- **Status**: posted
- **Notes**: <any observations>

---
```

Also update the tweet's status in the Discovered Tweets table to "engaged".

---

## Best Practices for Engaging X Content

### Replies
- Add value, not just agreement ("great point!" is worthless)
- Quote a specific part of the tweet to show you actually read it
- Share a contrarian or nuanced take when you have one
- Keep it concise - every word matters in 280 characters
- Avoid "reply guy" energy - be selective about what you reply to
- Reply early on viral tweets for maximum visibility

### Tweets
- Hook in the first 7 words (that's what shows in the timeline preview)
- Use threads for long-form content (number them: 1/, 2/, 3/)
- One idea per tweet - don't try to say everything at once
- Use visuals/media when possible (images get 2-3x more engagement)
- 1-2 hashtags max (X penalizes hashtag stuffing)
- End with a question or hot take to drive replies
- Best posting times: weekday mornings (8-10am) and evenings (6-8pm) in your audience's timezone

### Threads
- Start with a strong hook ending in "thread:" or a hook emoji
- Each tweet should stand alone (people may see individual tweets)
- End with a summary + CTA
- Retweet the first tweet after posting to resurface it

### General
- Consistency beats virality - tweet regularly
- Engage with others more than you broadcast
- Build genuine relationships through thoughtful replies
- Your bio is your first impression - keep it sharp

---

## Engagement Philosophy

### Do's
- Provide genuine value in every interaction
- Share insights that demonstrate authentic expertise
- Be transparent about who you are and your affiliations
- Build real relationships through consistent, quality engagement
- Amplify others' good work through thoughtful quote tweets

### Don'ts
- Never spam replies, mentions, or DMs
- Don't engage in tweets where your input isn't genuinely relevant
- Avoid generic replies - be specific and thoughtful
- Don't use X as a pure self-promotion channel
- Never create fake accounts or use bot-like behavior
- Don't engage in pile-ons, flame wars, or harassment
- Avoid follow/unfollow tactics to game follower counts
