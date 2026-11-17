# Gandalf_Editor
Set of video maker skills and agents

## Structure

- `plugins/gandalf-editor/skills/ceo/SKILL.md`: CEO skill. Loads automatically when you ask for a video (e.g. "let's create a new video") and delegates work to the subagents below
- `plugins/gandalf-editor/agents/investigator/`: researches TikTok/Instagram references and trends (`AGENT.md` plus any supporting files)
- `plugins/gandalf-editor/agents/screenwriter/`: writes the script and shot list (`AGENT.md` plus any supporting files)
- `plugins/gandalf-editor/agents/editor/`: edits the final video (`AGENT.md` plus any supporting files)
- New agents must be added to the `agents` list in `plugins/gandalf-editor/.claude-plugin/plugin.json`. Only listed files load, so other `.md` files in agent folders don't become agents.
- `productions/<slug>/`: one folder per video, used to pass work between agents (`brief.md` → `research.md` → `script.md` → `output/`)

## Usage

Install once from a terminal (the Claude desktop app's Code tab uses the same install):

```
claude plugin install gandalf-editor --marketplace srdjanmania/Gandalf_Editor
```

Then just ask for a video in any project, e.g. "Let's create a new video about…". Claude loads the CEO skill automatically. You can also start it directly with `/gandalf-editor:ceo`.

To try plugin changes locally without installing:

```
claude --plugin-dir ./plugins/gandalf-editor
```
