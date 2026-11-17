# Gandalf_Editor
Set of video maker skills and agents

## Structure

A generic short-form video team. The plugin holds no business details: the CEO gets them from your Claude project's instructions and files, and hands each specialist only what it needs.

- `plugins/gandalf-editor/skills/ceo/SKILL.md`: CEO skill. Loads automatically when you ask for a video (e.g. "let's create a new video") and coordinates the agents below
- `plugins/gandalf-editor/agents/<name>/AGENT.md`: one folder per specialist (plus any supporting files): `intake`, `investigator`, `analyst`, `screenwriter`, `editor`, `qa-controller`, `copywriter`
- New agents must be added to the `agents` list in `plugins/gandalf-editor/.claude-plugin/plugin.json`. Only listed files load, so other `.md` files in agent folders don't become agents.

## Usage

Install once from a terminal (the Claude desktop app's Code tab uses the same install):

```
claude plugin install gandalf-editor --marketplace srdjanmania/Gandalf_Editor
```

Then just ask for a video, e.g. "Let's create a new video about…". Claude loads the CEO skill automatically. You can also start it directly with `/gandalf-editor:ceo`.

To try plugin changes locally without installing:

```
claude --plugin-dir ./plugins/gandalf-editor
```
