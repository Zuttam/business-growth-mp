# Opportunity Master Plugin

A Claude Code plugin for sales automation with specialized SDR and Account Executive agents for LinkedIn-based prospecting and pipeline management.

## Features

### Agents

| Agent | Purpose |
|-------|---------|
| **SDR Agent** | Lead generation, LinkedIn prospecting, outreach campaigns |
| **Account Executive Agent** | Pipeline management, deal progression, sales strategy |

### Skills

| Skill | Command | Description |
|-------|---------|-------------|
| List Building | `/opportunity-master:list-building` | Build targeted lead lists from LinkedIn |
| Campaign Creation | `/opportunity-master:campaign-creation` | Create outreach campaigns with messaging sequences |
| Campaign Execution | `/opportunity-master:campaign-execution` | Execute campaigns and track progress |
| Lead Research | `/opportunity-master:lead-research` | Research prospects for personalization |

## Prerequisites

- **Claude in Chrome Extension**: Required for LinkedIn browser automation
- Browser must be open with LinkedIn logged in

## Installation

Add to your project's `.claude/settings.json`:

```json
{
  "enabledPlugins": {
    "opportunity-master@plugin-marketplace": true
  }
}
```

Or run with plugin directory:

```bash
claude --plugin-dir /path/to/plugin-marketplace/opportunity-master
```

## Data Storage

All data is stored in the `/business_growth/sales/` directory of your project. Directories are automatically created when the relevant agent starts:
- SDR Agent creates: `lead_lists/`, `campaigns/`, `templates/`
- Account Executive Agent creates: `opportunities/`

```
/business_growth/sales/
├── lead_lists/           # Prospect lists from LinkedIn
│   └── list_<name>/                  # e.g., list_sf_series_b_vp_engineering
│       ├── LIST.md                   # Lead data
│       └── icp.md                    # ICP definition
├── campaigns/            # Outreach campaigns
│   └── campaign_<name>/              # e.g., campaign_q1_outreach_fintech
│       ├── CAMPAIGN.md               # Campaign definition
│       └── leads/
│           └── <lead_name>/          # e.g., john_smith_acme
│               ├── execution.md      # Action log
│               └── research.md       # Lead research
├── opportunities/        # Sales opportunities (AE agent)
│   └── opp_<name>.md                 # e.g., opp_acme_corp_enterprise_deal
└── templates/            # Reusable message templates
```

**Naming Convention**: All entity names use snake_case (lowercase with underscores), include key identifying info, and are kept concise (3-5 words max).

## Usage Examples

### Build a Lead List

```
/opportunity-master:list-building VP Engineering at Series B SaaS companies in San Francisco
```

### Create an Outreach Campaign

```
/opportunity-master:campaign-creation list_sf_series_b_vp_engineering
```

### Execute Campaign Actions

```
/opportunity-master:campaign-execution campaign_q1_outreach_fintech run
```

### Research a Prospect

```
/opportunity-master:lead-research https://linkedin.com/in/johndoe
```

## LinkedIn Rate Limits

The plugin advises on LinkedIn's usage limits:

| Action | Limit |
|--------|-------|
| Profile views | ~30/hour, ~100/day |
| Connection requests | ~20-25/day |
| Messages | ~50-100/day |

Campaign execution uses a manual check-in approach - you invoke the skill periodically to process pending actions, giving you control over pacing.

## Workflow Example

1. **Define ICP** → Use list-building to define your ideal customer profile
2. **Build List** → Search LinkedIn and save prospects
3. **Research Top Leads** → Use lead-research for personalization
4. **Create Campaign** → Design messaging sequence
5. **Execute** → Run campaign with periodic check-ins
6. **Convert** → When leads respond, AE agent helps with pipeline

## Version History

- **0.1.0** - Initial release with SDR/AE agents and core skills

## Author

Hissuno
