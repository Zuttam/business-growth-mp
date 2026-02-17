# Instagram Engagement

## Prerequisites

Before engaging:
1. Load Instagram engagement strategy from `.business_growth/marketing/social/instagram/strategy.md` — if it doesn't exist, ask the user: **"No Instagram engagement strategy found. Would you like to create one before engaging?"** If yes, follow the strategy creation flow in [references/research.md](./research.md) Step 0. If no, proceed without it.
2. Business context must exist at `.business_growth/marketing/social/BUSINESS.md`
3. Posts should be discovered and saved to `.business_growth/marketing/social/instagram/{YYYY-MM}/{YYYY-MM-DD}.md`
4. User must be logged into Instagram in the browser (use login skill or log in manually)

---

## Option 1: Comment on Existing Post

### 1.1: Load and Evaluate Posts

```
Read .business_growth/marketing/social/instagram/{YYYY-MM}/{YYYY-MM-DD}.md
```

If today's file doesn't exist, check previous days or run Research first.

Evaluate post fit based on:
- **Recency**: Is the post still getting engagement? (< 12h ideal, < 48h acceptable)
- **Engagement**: Are people still commenting?
- **Relevance**: Can we provide genuine value in the comments?
- **Author**: Is this someone worth building a relationship with?
- **Caption**: Does the caption invite discussion (questions, opinions, advice)?

### 1.2: Draft Proposed Comment

Craft a comment that:
- Adds genuine value (not just emoji reactions like fire or clap)
- References something specific from the post caption or visual content
- Asks a thoughtful question or shares relevant experience
- Is conversational and authentic in tone
- Is 2-4 sentences (the sweet spot for Instagram comments)
- Is NOT salesy or promotional
- Uses 0-2 relevant hashtags only if natural (avoid hashtag stuffing in comments)
- Mentions product/service ONLY if directly relevant and helpful

### 1.3: ASK USER FOR APPROVAL

**CRITICAL**: Present to user:
```
Post Author: @<username>
Caption Preview: <first 1-2 lines>
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
find ("Add a comment..." placeholder or comment input) → computer (left_click) →
computer (type: comment text) →
find ("Post" button next to comment input) → computer (left_click) → screenshot (verify posted)
```

### 1.5: Log Engagement

Update today's file at `.business_growth/marketing/social/instagram/{YYYY-MM}/{YYYY-MM-DD}.md`, appending to the `## Engagement Log` section:

```markdown
### HH:MM - Comment
- **Post Author**: @<username>
- **Caption Preview**: <first line>
- **URL**: <url>
- **Content**:
> <comment text>
- **Status**: posted
- **Notes**: <any observations>

---
```

Also update the post's status in the Discovered Posts table to "engaged".

---

## Option 2: Follow Account

### 2.1: Load and Evaluate Accounts

```
Read .business_growth/marketing/social/instagram/{YYYY-MM}/{YYYY-MM-DD}.md
```

Review the "Accounts to Follow" section. Evaluate based on:
- **Relevance**: Is this account in the target niche?
- **Activity**: Do they post regularly and engage with followers?
- **Audience Overlap**: Does their audience match our target demographic?
- **Engagement Quality**: Do they have genuine engagement (not bot-inflated)?

### 2.2: ASK USER FOR APPROVAL

**CRITICAL**: Present to user:
```
Account: @<username>
Name: <display name>
Bio: <bio>
Followers: <count>
URL: <profile url>
Relevance: <why this account matters>

Should I follow this account? (yes/no)
```

**Wait for explicit "yes" before proceeding.**

### 2.3: Follow Account via Browser MCP

Upon approval:
```
navigate (profile URL) → read_page (verify profile) →
find ("Follow" button) → computer (left_click) → screenshot (verify followed)
```

### 2.4: Log Engagement

Update today's file at `.business_growth/marketing/social/instagram/{YYYY-MM}/{YYYY-MM-DD}.md`, appending to the `## Engagement Log` section:

```markdown
### HH:MM - Follow
- **Account**: @<username>
- **Name**: <display name>
- **URL**: <profile url>
- **Relevance**: <why followed>
- **Status**: followed
- **Notes**: <any observations>

---
```

Also update the account's status in the "Accounts to Follow" table to "followed".

---

## Option 3: Check Replies & Follow Up

Run this as part of every daily engagement session, ideally before posting new comments. Check for replies to your previous comments and respond to meaningful ones.

### 3.1: Load Recent Engagement History

```
Read .business_growth/marketing/social/instagram/{YYYY-MM}/{YYYY-MM-DD}.md (today and past 2-3 days)
```

Identify posts where comments were previously posted (status: "engaged" in Discovered Posts or entries in Engagement Log).

### 3.2: Navigate to Engaged Posts

For each previously engaged post:
```
navigate (post URL) → screenshot → read_page or get_page_text
```

Check for:
- **Author replies** to your comment (highest priority - the post creator responded)
- **User replies** to your comment (someone engaged with your comment)
- **Likes on your comment** (signals resonance, no action needed)

### 3.3: Evaluate Which Replies Need a Response

Respond when:
- The post author replies to your comment (highest priority)
- Someone asks a follow-up question
- A reply creates an opening to add more value naturally
- Someone shares relevant experience that merits acknowledgment

Skip responding when:
- The reply is just an emoji or "thanks"
- The thread has gone cold (>48h since last activity)
- Engaging further would seem pushy or self-promotional
- The reply is hostile or trolling (never engage with bad faith)

### 3.4: Draft Follow-Up Reply

Follow-up reply guidelines:
- Keep it shorter than your original comment
- Be conversational, not lecturing
- Thank the person if they validated your point or shared a helpful response
- Add one new insight max - don't repeat yourself
- Match the tone of the person you're replying to

### 3.5: ASK USER FOR APPROVAL

**CRITICAL**: Before posting any follow-up reply, present to user:
```
Post: <original post URL>
Their reply: <what they said>

Proposed response:
---
<drafted reply>
---

Should I post this reply? (yes/no)
```

**Wait for explicit "yes" before proceeding.**

### 3.6: Post Reply via Browser MCP

Upon approval:
```
navigate (post URL) → find (the reply to your comment) →
find ("Reply" link under the reply) → computer (left_click) →
computer (type: response text) →
find ("Post" button) → computer (left_click) → screenshot (verify posted)
```

### 3.7: Log Follow-Up

Update the daily file's Engagement Log:

```markdown
### HH:MM - Follow-Up Reply
- **Post**: <post URL>
- **Original Comment Date**: <date of original comment>
- **Their Reply**: <what they said>
- **Our Response**:
> <reply text>
- **Status**: posted
- **Notes**: <any observations>

---
```

---

## Best Practices for Engaging Instagram Content

### Comments
- Add value beyond emoji reactions ("fire emoji" adds nothing)
- Reference something specific from the caption or visual content
- Ask a genuine question that shows you engaged with the content
- Keep it authentic and conversational - Instagram penalizes generic/bot-like comments
- 2-4 sentences is the sweet spot
- Reply to other commenters to build visibility in the thread
- Engage within the first 12 hours for maximum algorithmic visibility

### Following
- Follow accounts in your niche to build a relevant network
- Engage with their content before and after following (commenting is more valuable than just following)
- Avoid mass follow/unfollow tactics - Instagram detects and penalizes this
- Quality over quantity: 10-20 strategic follows per day maximum
- Focus on accounts that actively engage with their followers

### Rate Limits
- Instagram aggressively limits automated-looking actions
- Wait between comments (at least 30-60 seconds between actions)
- Don't follow more than 10-20 accounts per day
- Rapid actions can trigger temporary action blocks (24-48h)
- If you encounter an action block, stop all activity and wait

### General
- Consistency beats virality - engage daily rather than in bursts
- The algorithm favors accounts that generate genuine engagement
- Profile bio is your landing page - keep it clear and relevant
- Engage with content you genuinely find interesting or valuable

---

## Engagement Philosophy

### Do's
- Provide genuine value in every comment
- Share insights that demonstrate authentic expertise
- Be transparent about who you are and your affiliations
- Build real relationships through consistent, quality engagement
- Engage with content you genuinely find interesting or valuable

### Don'ts
- Never spam comments or use generic copy-paste responses
- Don't use automated like/follow/comment bots
- Avoid engagement pods or artificial reciprocity schemes
- Don't use Instagram as a pure self-promotion channel
- Never create fake accounts or engage in inauthentic behavior
- Don't rapid-fire follow/unfollow to game follower counts
- Avoid excessive hashtags in comments (looks spammy)
