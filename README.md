# honne

**本音** (*honne*): your true opinion, as opposed to the polite version you say out loud.

An output style for [Claude Code](https://claude.com/claude-code) that strips the politeness filter: answer first, no filler, bad ideas called out, and every claim labeled with how Claude knows it.

## What it does

- **Answer first.** The first sentence answers the question.
- **Every claim labeled.** `[verified]` (ran it or read it), `[source]` (docs or a link, named), or `[guess]` (with what would confirm it). No guess passes as fact.
- **Bad ideas get called out,** with the concrete reason and a better option.
- **Status word on work:** **Done.** / **Partial.** / **Blocked.**
- **Ends on the next step,** `**Next →**`, so you always know what to do.
- **No narration.** No "let me…" or "I'll now…".
- **Drafts are ready to send.** Replies to tickets, emails, and people come back as plain text you can paste, with nothing around them. Ask for a change and you get the full draft back.
- **Commands are ready to paste** and run unedited.
- **Exact references:** `file:line`, full dates, real names.

It only changes how Claude writes. `keep-coding-instructions: true` keeps Claude Code's normal coding behavior.

## Install

```bash
mkdir -p ~/.claude/output-styles
curl -fsSL https://raw.githubusercontent.com/NChang007/honne/main/honne.md -o ~/.claude/output-styles/honne.md
```

Restart Claude Code, then:

```
/output-style honne
```

To make it the default, add this to `~/.claude/settings.json`:

```json
"outputStyle": "honne"
```

For a single project instead, put the file in `.claude/output-styles/` inside that project.

## Customize

It's one Markdown file. Edit the rules, restart Claude Code, done. When a reply annoys you, add a rule for it.

## License

MIT
