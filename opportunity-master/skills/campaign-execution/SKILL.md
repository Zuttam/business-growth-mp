---
name: campaign-execution
description: Execute LinkedIn outreach campaigns by sending connection requests and messages. Use when user wants to run a campaign, execute outreach, check campaign status, send messages, or track campaign progress. Can be invoked with optional campaign_id and action (run, status, pause, resume).
---

# Campaign Execution Skill

Execute LinkedIn outreach campaigns by performing due actions and tracking progress. Uses a manual check-in approach where users invoke this skill periodically to process pending actions.

## Process

### Step 1: Load Campaign

If `campaign_id` not provided:
1. Search for campaigns in `.business_growth/sales/campaigns/`
2. Display campaigns with status and progress
3. Ask user to select campaign

Load the campaign's `CAMPAIGN.md` and `LIST.md` files from the campaign folder (`.business_growth/sales/campaigns/<campaign_id>/`).

### Step 2: Determine Action

Based on `action` parameter or ask user:

| Action | Description |
|--------|-------------|
| `run` | Execute all due actions for leads |
| `status` | Show campaign progress without actions |
| `pause` | Set campaign status to paused |
| `resume` | Set campaign status to running |

### Step 3: For "status" Action

Display campaign summary:
- Campaign name and status
- Total leads in target list
- Breakdown by execution status
- Recent activity log
- Pending actions count

### Step 4: For "run" Action

Process each lead in the target list:

#### 4a. Check/Create Execution File

For each lead, check if execution file exists at:
`.business_growth/sales/campaigns/campaign_<name>/leads/<lead_name>/execution.md`

**Lead Naming**: Generate meaningful snake_case names for leads based on their name and company (e.g., `john_smith_acme`, `sarah_jones_techcorp`). Keep names concise, lowercase with underscores.

If not exists, create it:

```markdown
# Execution: <Lead Name>

## Lead Info
- **Name**: <name>
- **LinkedIn**: <url>
- **Company**: <company>
- **Campaign**: campaign_<name>   # e.g., campaign_q1_outreach_fintech

## Status
- **Current**: pending
- **Current Step**: 1
- **Next Action**: connection_request
- **Next Action Time**: <now>

## Action Log
<!-- Actions will be logged here -->
```

#### 4b. Check If Action Due

Read execution file and check:
1. Is status `pending` or `in_progress`?
2. Is current date >= next action time?
3. Has previous step completed successfully?

If all true, action is due.

#### 4c. Execute Due Action

Based on action type:

**Connection Request**:
1. Navigate to lead's LinkedIn profile
2. Click "Connect" button
3. Add personalized note from template
4. Send connection request
5. Take screenshot for verification

**Message**:
1. Navigate to lead's profile or messaging
2. Open message compose
3. Enter personalized message from template
4. Send message
5. Take screenshot for verification

**Important**: Replace template tokens with lead data:
- `{{first_name}}` → Lead's first name
- `{{company}}` → Lead's company
- `{{title}}` → Lead's title
- `{{custom}}` → Custom personalization from research.md if exists

#### 4d. Log Action and Update Status

Update `execution.md`:

```markdown
## Status
- **Current**: in_progress
- **Current Step**: 2
- **Next Action**: message
- **Next Action Time**: <calculated based on sequence timing>

## Action Log

### <timestamp>
- **Step**: 1
- **Type**: connection_request
- **Content**: <actual message sent>
- **Outcome**: sent
- **Screenshot**: <reference if taken>
```

#### 4e. Handle Special Cases

**Connection Accepted**:
- Update execution status to reflect acceptance
- Calculate next action time for welcome message

**Reply Received**:
- Set status to `replied`
- No more automated actions
- Flag for manual follow-up

**Failed Action**:
- Log error in execution file
- Set status to `failed` with reason
- Continue with next lead

### Step 5: Rate Limit Management

Track actions taken and advise on limits:
- Connection requests: ~20-25/day
- Messages: ~50-100/day
- Profile views: ~30/hour

When approaching limits:
1. Pause execution
2. Inform user of limits reached
3. Suggest resuming after cooldown period
4. Calculate when safe to resume

### Step 6: Report Progress

After processing all due actions, provide summary:

```
## Campaign Execution Summary

**Campaign**: <name>
**Execution Time**: <timestamp>

### Actions Taken
- Connection Requests Sent: X
- Messages Sent: Y
- Total Actions: Z

### Lead Status Breakdown
- Pending: X leads
- In Progress: Y leads
- Replied: Z leads (🎉)
- Completed: W leads
- Failed: V leads

### Next Check-In
Recommend checking back in: <calculated time>
Reason: <rate limit cooldown / sequence timing>

### Leads Requiring Attention
- <Lead Name>: <reason - e.g., "Replied to connection request">
```

### Step 7: Update Campaign Metrics

Update `CAMPAIGN.md` performance metrics section with current counts.

## Execution Statuses

| Status | Meaning |
|--------|---------|
| `pending` | Not yet started |
| `in_progress` | Sequence in progress, awaiting next step |
| `replied` | Lead replied, stop automation |
| `completed` | All steps executed |
| `failed` | Error occurred, needs review |

## Browser Tools Used

| Tool | Purpose |
|------|---------|
| `tabs_context_mcp` | Get browser context |
| `navigate` | Go to LinkedIn profiles |
| `read_page` | Verify page state |
| `find` | Locate buttons and inputs |
| `form_input` | Enter message text |
| `computer` | Click, scroll, screenshot |

## Error Handling

Common issues and responses:

| Issue | Response |
|-------|----------|
| Profile not found | Mark as failed, log reason |
| Connect button unavailable | May already be connected, verify |
| Rate limit warning | Stop execution, report to user |
| Login required | Ask user to log in manually |
| Message failed to send | Retry once, then mark failed |

## Manual Check-In Approach

This skill is designed for periodic manual invocation:

1. User invokes skill when ready to execute
2. All due actions are processed
3. Summary provided with next check-in time
4. User invokes again when ready

This approach:
- Respects LinkedIn rate limits
- Gives user control over timing
- Allows review between batches
- Avoids continuous automation flags
