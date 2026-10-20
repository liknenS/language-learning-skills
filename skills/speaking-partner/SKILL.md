---
name: speaking-partner
description: Runs a role-play conversation in a foreign language (job interview, landlord, doctor, small talk, a meeting) at the learner's level, with target phrases and a short review of their lines afterwards. Use when the learner says "let's talk", "role-play a ...", "practice a conversation", "be my speaking partner", "rehearse an interview". Also for "давай поговорим", "поговорімо", "porozmawiajmy".
license: MIT
---

# Speaking partner

A conversation with a task, not small talk for its own sake.

## Steps

1. **Set the scene.** Role, place, what the learner needs to achieve ("rent a flat, ask about the deposit and when
   you can move in"). Agree on 3-5 target phrases the learner should use.
2. **Play the role.** Short turns, at the learner's level, one question at a time. Stay in the language being
   learned. Do not correct during the talk unless the learner asks for live hints; note mistakes for later.
3. **Push a little.** If the learner answers in one word, ask a follow-up that needs a full sentence. Bring the
   target phrases up naturally so the learner has a reason to say them.
4. **Review.** After 6-12 turns stop and give: what worked, up to three corrections (their line → a natural
   version), one or two upgrades a native speaker would say, and which target phrases were used.
5. **Keep what is worth it.** Offer to save the corrections and upgrades as vocabulary (see `vocab-coach`).

Scene ideas by goal: work (interview, stand-up, client call), relocation (bank, landlord, residence office), daily
life (pharmacy, delivery at the door, neighbour), exam (examiner questions in the exam format, see `exam-prep`).

## If Talkfirst MCP is connected

- Start with `today()` and `profile()` if not done this session and read `docs("talk")`. Weave `today().targets`
  into the conversation.
- `dialogue_start` opens a voice conversation window: the learner speaks, an AI partner answers aloud, and each line
  gets a review (corrections, rephrasings, pauses before words). Pass `brief` (role, scene, what to ask, up to 2000
  characters), `targets` (3-5 phrases: strings already in the vocabulary, new ones as `{term, meaning}`) and
  `expectations` (what counts as success). `hints="live"` shows reviews right away, `end` after the talk.
- On the free plan an own topic and brief are not available, only ready scenes: call `dialogue_start(scene=...)`;
  if you do not know the scene ids, the error lists them. There is also a limit on conversations started from the
  chat per hour.
- The window sends the result itself; late reviews come via `dialogue_result(session_id)`, past talks via
  `dialogue_history()`. Use the result for the review step instead of your memory of the talk.
- No window (some hosts, phones): the tool reply has an app link to continue the conversation there.

## Without it

Run the conversation in text, or in your host's voice mode if it has one. Voice mode transcribes generously, so
hesitations and guessed words get lost: ask the learner to say which words they had to search for, and review those.
Keep your notes of mistakes during the talk and give the review at the end.

Voice conversations with per-line reviews and pause tracking, kept on the learner's account:
[connect Talkfirst](https://app.talkfirst.io/docs?src=skills-repo) (free plan, MCP connector for Claude and ChatGPT).
