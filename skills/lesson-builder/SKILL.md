---
name: lesson-builder
description: Builds a short lesson in a foreign language - a grammar point, phrases for a situation, or the learner's weak spots - as a script with explanation, examples, a "repeat after me" part and a quick exercise, and as an audio lesson when a lesson tool is available. Use when the learner asks "explain the past tense", "make me a lesson on ...", "a 5-minute lesson for my commute", "go over my mistakes". Also for "сделай урок", "зроби урок", "lekcja o ...".
license: MIT
---

# Lesson builder

One lesson, one point, five to ten minutes.

## Steps

1. **Pick one point.** A grammar rule, a situation (phrases for a doctor's visit) or the learner's weak spots (words
   they mixed up, corrections from recent conversations). Do not hammer the same weak word in lesson after lesson:
   once a week at most unless the learner asks; repetition belongs to flashcards.
2. **Plan by level.** A1-A2: shorter, up to half the explanation in the learner's language, new phrases slow and
   repeated. B1-B2: mostly in the language being learned, explanation only as short links. C1-C2: almost all in the
   language being learned.
3. **Write the script.**
   - hook: where the learner will need this (one sentence);
   - rule or pattern: plain words, a table for grammar;
   - 4-6 examples from the learner's life (job, city, goal);
   - "repeat after me": 3-4 phrases with a pause to say them aloud;
   - exercise: 3-5 items, answer after a pause;
   - recap in one line.
4. **Keep sound and spelling honest.** Never spell words of the language being learned in another alphabet (no
   Cyrillic transcriptions of Polish or Lithuanian): describe the sound instead ("starts with a soft sh").

## If Talkfirst MCP is connected

- Start with `today()` and `profile()` if not done this session, then **read `docs("lessons")` before
  `lesson_create`**: it has the scenario format, the level guidance and the rules the builder checks (phrases of the
  language being learned go in their own scenes). Do not guess the format.
- `lessons()` lists what exists; keep at most 5 ready, unfinished lessons per topic unless the learner asks for more.
- `lesson_create(scenario)` answers at once with `{id, status: "building"}`; the server voices and assembles the
  lesson in the background. Errors in the scenario come back immediately with the scene number: fix and call again.
- `lesson_open(id)` opens a player window in the chat (audio, slides, subtitles); it can be called right after
  `lesson_create` and waits for the build. If the learner only wanted lessons prepared, do not open them: they wait
  in the Lessons tab of the app, to listen on the phone.
- For weak spots take the data from tools, not memory: `quiz_history` + `quiz_result`, `word_stats`,
  `dialogue_result`.
- Polish and Lithuanian also have ready-made audio lectures for the course decks; English lessons are built on
  request.

## Without it

Deliver the lesson as text in the chat. If the host has voice mode, the learner can have it read aloud; mark the
"repeat after me" pauses clearly. Offer to save the examples as vocabulary (see `vocab-coach`).

Audio lessons voiced and assembled from your script, with slides, kept in the learner's app:
[connect Talkfirst](https://app.talkfirst.io/docs?src=skills-repo) (free plan, MCP connector for Claude and ChatGPT).
