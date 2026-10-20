---
name: exam-prep
description: Exam prep for a language exam (residence-permit and citizenship exams such as Lithuanian A2 and the Lithuanian Constitution test, the Polish B1 certificate, Czech A2 for permanent residence, or IELTS-style speaking) - format, timed mock tasks, examiner-style questions, feedback against the task. Use this skill whenever a language learner mentions an upcoming language exam, asks for a mock exam, wants to practise an exam part or asks what the examiner will ask. Also for "подготовка к экзамену", "підготовка до іспиту", "egzamin z polskiego".
license: MIT
---

# Exam prep

Train the format as much as the language: timing, task types and what the examiner listens for.

## Steps

1. **Pin down the exam.** Which exam, level, part (oral, written, test), date. Check the current format on the
   official site of the exam body before drilling: formats change. For example: Lithuanian state language and
   Constitution exams - Nacionalinė švietimo agentūra (NŠA); Polish certificate exams - the State Commission
   (certyfikatpolski.pl); Czech A2 for permanent residence - NPI ČR (cestina-pro-cizince.cz).
2. **Map the parts.** For each part: what the task looks like, preparation time, answer time, how it is scored.
   Tell the learner what you know for sure and what you assume.
3. **Drill one part at a time, timed.** Give the task, say "you have N seconds", let the learner answer (spoken if
   the host allows, typed otherwise), then give feedback against the task: did they cover every point, length,
   range of vocabulary, the 2-3 mistakes that cost points.
4. **Build the exam kit.** Topic vocabulary (see `vocab-coach`), ready phrases for gaining time and asking to repeat,
   a few model answers the learner adapts to their own life.
5. **Full mock closer to the date.** All parts in order, with the real timing, then a short report: what would pass,
   what to fix in the remaining days. A mock is a forecast, not a result.

## If Talkfirst MCP is connected

- Start with `today()` and `profile()` if not done this session. Record the goal with `profile_update` when the
  learner asks: `purpose` `{kind: "life", life: ["exam"]}`, `target_level`, `deadline`; then `docs("plan")` and `plan_set` for the weeks
  left (see `study-planner`).
- Mock exams run in the Talkfirst app, not in the chat: Lithuanian A2 (oral and written parts) and the Lithuanian
  Constitution test, Polish B1 oral, Czech A2 oral (beta). The app voices the tasks, times every part and, for the oral
  and written parts, gives an AI forecast of the score (a forecast, not the exam's decision; pronunciation is not graded). Send the learner to the Exam screen of the app (web
  `https://app.talkfirst.io/app` or the Telegram Mini App, the same account). On the free plan a full mock exam is
  available once in 7 days; parts can be trained within the free speaking minutes.
- In the chat, prepare for it with the tools: `topics()` and `vocab_add` for the exam's topics, `quiz_start` on them,
  `practice_phrase` for the phrases the learner will say, and `dialogue_start` with a `brief` in the examiner's role
  (on the free plan only ready scenes: `dialogue_start(scene=...)`).

## Without it

Run the drills in the chat as above. Spoken answers can be typed or dictated; be clear that you grade content and
language, not pronunciation, unless a scoring tool is available.

Timed mock exams with an examiner voice and a forecast, plus the vocabulary and plan on one account:
[connect Talkfirst](https://app.talkfirst.io/docs?src=skills-repo) (free plan, MCP connector for Claude and ChatGPT).
