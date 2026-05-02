# Claude Code Transcripts

This directory contains transcripts of Claude Code conversations for documentation, reference, and retroactive analysis.

## Directory Structure

```
claude-code-transcripts/
├── raw/                    # Complete verbatim transcripts with thought process
├── processed/              # Cleaned/formatted transcripts
├── summaries/              # Executive summaries and reports
├── metadata/               # Session information and analytics
└── README.md              # This file
```

## Folder Purposes

### `/raw/`
Complete, unedited transcripts including:
- Full conversation flow
- User messages
- Assistant responses
- Internal reasoning and thought process
- Tools used and why
- Analysis performed
- Decisions made

**Format**: Markdown with embedded metadata
**Naming**: `YYYY-MM-DD-topic-description.md`

### `/processed/`
Cleaned transcripts for easier reading:
- Formatted for readability
- Sections organized
- Code blocks highlighted
- Key insights emphasized

**Format**: Markdown
**Naming**: `YYYY-MM-DD-topic-description.md`

### `/summaries/`
Executive summaries and reports:
- Conversation overview
- Key decisions
- Artifacts created
- Action items
- Next steps

**Format**: Markdown
**Naming**: `YYYY-MM-DD-topic-summary.md`

### `/metadata/`
Structured session information:
- Session ID
- Model used
- Tools executed
- Files modified
- Statistics
- Topics covered

**Format**: JSON
**Naming**: `YYYY-MM-DD-session-info.json`

## File Naming Convention

All transcript files follow this pattern:
```
YYYY-MM-DD-brief-topic-description.ext
```

Examples:
- `2025-02-06-infrastructure-design-conversation.md`
- `2025-02-06-infrastructure-design-summary.md`
- `2025-02-06-session-info.json`

## Usage

### Viewing a Transcript
```bash
# View raw transcript with thought process
cat raw/2025-02-06-infrastructure-design-conversation.md

# View summary
cat summaries/2025-02-06-infrastructure-design-summary.md

# View metadata
cat metadata/2025-02-06-session-info.json | jq
```

### Searching Transcripts
```bash
# Find conversations about a topic
grep -r "incident tracking" raw/

# Find sessions using specific tools
jq '.tools_used' metadata/*.json

# Find conversations by date range
ls raw/2025-02-*
```

### Integration with Incident Tracker
These transcripts can be imported into the incident tracking system:
1. Use chat import MCP server
2. Extract incident information
3. Link to formal incident reports
4. Enrich incidents with conversation context

## Current Transcripts

### 2026-02-06: Infrastructure Design & Incident Tracking
**Topic**: OpenAI Cookbook analysis and medical/work incident tracker design  
**Files** (Note: filenames show "2025-02-06" due to typo, actual session date is 2026-02-06):
- `raw/2025-02-06-infrastructure-design-conversation.md` - Complete transcript
- `summaries/2025-02-06-infrastructure-design-summary.md` - Summary report
- `metadata/2025-02-06-session-info.json` - Session metadata

**Key Topics**:
- Repository organization patterns
- Metadata-driven architecture
- CI/CD automation
- Incident tracking system design
- Chat integration for retroactive documentation
- MCP server design
- Git operations and stop hooks
- Conversation continuation and export

**Artifacts Created**:
- Complete infrastructure documentation (~18,000 words)
- 3 MCP server designs
- 6 incident templates
- 8 slash commands
- Security framework
- This transcript system (meta-documentation)

**Session Details**:
- Messages: 12 interactions
- Commit: `97f218b` on branch `claude/plan-development-8FVvW`
- Timestamp: 2026-02-06 03:36:15 UTC
- First message: "we are in plan mode"
- Updated: Includes conversation continuation through export request

## Best Practices

### When to Create Transcripts
- Complex technical discussions
- System design sessions
- Decision-making conversations
- Learning/teaching sessions
- Incident documentation (real-time)
- Planning sessions
- Troubleshooting discussions

### What to Include
- ✅ Complete conversation flow
- ✅ Internal reasoning (thought process)
- ✅ Tools and commands executed
- ✅ Files read and modified
- ✅ Decisions made and why
- ✅ Key insights
- ✅ Next steps

### What to Exclude
- ❌ Sensitive personal information
- ❌ API keys or credentials
- ❌ Confidential business data
- ❌ Medical records (unless encrypted)

## Automation

### Auto-generate Transcript
```bash
# Request transcript at end of session
/generate-transcript

# With options
/generate-transcript --include-thought-process --summary
```

### Batch Processing
```bash
# Process multiple sessions
python scripts/batch_process_transcripts.py --directory ./sessions/
```

## Integration Points

### With Obsidian
- Link transcripts to projects: `[[2025-02-06-infrastructure-design-conversation]]`
- Tag for categorization: `#transcript #infrastructure #design`
- Use Dataview to query transcripts

### With Incident Tracker
- Link transcripts to incidents
- Extract incident data automatically
- Enrich incident reports with conversation context

### With Git
- Transcripts are version controlled
- Commit after each session
- Use branches for different projects

## Metadata Schema

Each transcript has associated metadata:

```json
{
  "session_id": "string",
  "date": "YYYY-MM-DD",
  "model": "model-id",
  "mode": "plan|chat|code",
  "repository": "string",
  "branch": "string",
  "conversation_metadata": {
    "total_messages": number,
    "duration_estimate": "string",
    "topic": "string"
  },
  "tools_used": {},
  "deliverables": {},
  "major_topics": [],
  "key_innovations": [],
  "next_steps_available": []
}
```

## Contributing

When adding transcripts:
1. Follow naming conventions
2. Include all three files (raw, summary, metadata)
3. Update this README with new transcript entry
4. Commit with descriptive message

## Questions?

- For transcript requests: Use `/generate-transcript` command
- For format questions: See examples in this directory
- For integration: Check incident tracker documentation

---

## Known Issues

- **Filename Date Typo**: The first transcript files are named `2025-02-06-*` but the actual session date is `2026-02-06`. This was a typo during file creation. The files remain with the incorrect year prefix to avoid breaking existing links and references.

---

*Last updated: 2026-02-06*
*Transcripts: 1 (with continuation updates)*
*Total conversations documented: 1 (12 messages)*
*Total words: ~18,000*
