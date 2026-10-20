# Language learning skills

Agent Skills that turn Claude (or any agent that reads `SKILL.md`) into a language tutor that keeps a method:
vocabulary with spaced repetition, pronunciation drills, role-play conversations, short lessons, a weekly plan and
exam practice. Each skill works on its own in a plain chat. Each one also says what to do when the optional
[Talkfirst](https://talkfirst.io/?utm_source=skills-repo&utm_medium=catalog) MCP connector is connected, which adds
storage, recordings with scores and voice conversations.

| Skill | Use it for | Example request |
|---|---|---|
| [vocab-coach](skills/vocab-coach/SKILL.md) | pick words from a text or chat, save them, review with spaced repetition | "Take the phrases worth learning from this email and quiz me tomorrow" |
| [pronunciation-coach](skills/pronunciation-coach/SKILL.md) | sounds, stress, minimal pairs, word-by-word feedback | "How do I say *przepraszam*? Check me" |
| [speaking-partner](skills/speaking-partner/SKILL.md) | role-plays with target phrases and a review afterwards | "Be a landlord in Vilnius, I want to rent a flat" |
| [lesson-builder](skills/lesson-builder/SKILL.md) | a 5-10 minute lesson on one point or on your weak spots | "A short lesson on the Polish past tense for my commute" |
| [study-planner](skills/study-planner/SKILL.md) | goal, deadline and a weekly plan you can check | "I need B2 by June, plan my weeks" |
| [exam-prep](skills/exam-prep/SKILL.md) | exam format, timed mock tasks, feedback against the task | "Prepare me for the Lithuanian A2 speaking part" |

Requests and explanations can be in any language: the skills list trigger phrases in English, Russian, Ukrainian and
Polish, and the agent explains in the language you talk to it in.

## Install

### Claude Code (plugin)

```
/plugin marketplace add liknenS/language-learning-skills
/plugin install language-learning@language-learning-skills
```

Or copy single skills: `cp -r skills/vocab-coach ~/.claude/skills/` (personal) or into `.claude/skills/` of a
project.

### Claude.ai and the Claude desktop app

Download a skill ZIP from [Releases](https://github.com/liknenS/language-learning-skills/releases) (or zip one folder
from `skills/` yourself), then upload it in the Skills section of Settings → Capabilities. Skills need a paid plan and
code execution enabled. The Skills API (`/v1/skills`) takes the same folders.

### Other agents

The skills follow the open [Agent Skills](https://agentskills.io) format: plain Markdown with `name` and
`description` frontmatter. Put the folders where your agent looks for skills, for example `~/.agents/skills/` for
Codex CLI (`cp -r skills/* ~/.agents/skills/`), or paste a `SKILL.md` into a project's instructions.

## Optional: Talkfirst MCP connector

Without a connector the agent keeps the vocabulary and plan in files or in the chat, and cannot grade your
pronunciation. With [Talkfirst](https://talkfirst.io/?utm_source=skills-repo&utm_medium=catalog) connected the same
skills switch to its tools:

- vocabulary and flashcards with spaced repetition, quizzes in a window in the chat;
- a recording window with a score for the phrase and for each word;
- voice conversations with an AI partner and a review of every line, pauses included;
- audio lessons voiced from the agent's script, ready-made lectures for Polish and Lithuanian;
- a weekly plan with the fact counted by the server, and pace towards a target level;
- mock exams in the app: Lithuanian A2 and the Constitution test, Polish B1, Czech A2 (beta).

Courses: English, Polish, Lithuanian, Czech (beta); explanations in English, Russian or Ukrainian. The same account
works in the web app and the Telegram Mini App. Free plan available.

Connect: `https://mcp.talkfirst.io/mcp` (remote MCP, OAuth; sign in with an email code or Telegram).

- Claude.ai / desktop: Settings → Connectors → Add custom connector, paste the URL.
- Claude Code: `claude mcp add --transport http talkfirst https://mcp.talkfirst.io/mcp`, then `/mcp` to sign in.
- ChatGPT: developer mode connectors, where your plan and region have them.

Current steps: [Talkfirst docs](https://app.talkfirst.io/docs?src=skills-repo).

Disclosure: these skills are written by the Talkfirst developer. They do not require Talkfirst and do not call it
unless you connect it.

## License

MIT
