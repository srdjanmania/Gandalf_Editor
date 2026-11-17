# video-maker
Set of video maker skills and agents

## Structure

- `plugins/video-maker/skills/ceo/SKILL.md`: CEO skill. Loads automatically when you ask for a video (e.g. "let's create a new video") and delegates work to the subagents below
- `plugins/video-maker/agents/investigator/`: researches TikTok/Instagram references and trends (`AGENT.md` plus any supporting files)
- `plugins/video-maker/agents/screenwriter/`: writes the script and shot list (`AGENT.md` plus any supporting files)
- `plugins/video-maker/agents/editor/`: edits the final video (`AGENT.md` plus any supporting files)
- New agents must be added to the `agents` list in `plugins/video-maker/.claude-plugin/plugin.json`. Only listed files load, so other `.md` files in agent folders don't become agents.
- `productions/<slug>/`: one folder per video, used to pass work between agents (`brief.md` → `research.md` → `script.md` → `output/`)

## Usage

Install the plugin, then just ask for a video in any project, e.g. "Let's create a new video about…". Claude loads the CEO skill automatically. You can also start it directly with `/video-maker:ceo`.

To try plugin changes locally without installing:

```
claude --plugin-dir ./plugins/video-maker
```
