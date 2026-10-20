---
name: study-planner
description: Study planner for a foreign language - sets a goal (target level and deadline) and agrees a realistic weekly plan - minutes of own speech, quizzes, conversations, lessons - then compares the plan with what was done. Use this skill whenever a language learner asks for a study plan or schedule, names a target level or date ("B2 by June"), asks how much to practise or whether they are on track. Also for "составь план занятий", "склади план навчання", "plan nauki".
license: MIT
---

# Study planner

A plan is a few numbers per week that the learner agrees to and that can be checked.

## Steps

1. **Goal.** Current level (self-assessed is fine), target level, deadline, what for (work, exam, relocation).
   Write it down in one sentence and confirm it.
2. **Budget.** How many days a week and minutes a day the learner really has. Plan for the bad week, not the good one.
3. **Weekly targets.** Use a few countable things: minutes of own speech, quizzes or review sessions, conversations,
   lessons. Add one focus per week ("past tense", "phrases for the bank").
4. **Check honestly.** At the start of each session compare last week's plan with what happened. Behind: cut the
   plan or move the deadline together with the learner, don't just add more.
5. **Rough pace.** Moving one CEFR level usually takes months of regular practice, more at higher levels. Say
   "about" and avoid exact promises.

## If Talkfirst MCP is connected

- Start with `today()` and `profile()` if not done this session; read `docs("plan")` and `docs("pace")`.
- Goal: `profile_update` with `level`, `target_level`, `deadline`, `purpose`, only when the learner asks (changing
  the level or the target restarts the pace estimate).
- Plan: `plan()` returns this week and past weeks with `fact` counted by the server (`speech_min`, `quizzes`,
  `dialogues`, `lessons`). `plan_set(weeks)` replaces the plan from the current week on, up to 12 weeks ahead, each
  week starting on a Monday. Agree the numbers with the learner first.
- Pace: talk about it only from the `pace` field of `today()` / `plan()` (minutes a week the goal needs, the current
  average, `status` such as `on_track` or `behind`, estimated dates), never from your own guess.
- Standing agreements ("explain in English, correct only meaning-changing mistakes") go to `notes_set`; the next chat
  reads them with `notes()`.

## Without it

Keep the goal and the plan in a file if you can write files (`plan.md`: goal, weekly targets, a log line per week),
otherwise give the learner a short block to paste at the start of the next chat. Ask for the week's numbers yourself
at check-in; they are self-reported.

Plan and fact counted by the server, visible in every new chat:
[connect Talkfirst](https://app.talkfirst.io/docs?src=skills-repo) (free plan, MCP connector for Claude and ChatGPT).
