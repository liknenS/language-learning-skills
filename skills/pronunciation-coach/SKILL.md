---
name: pronunciation-coach
description: Coaches pronunciation of phrases in a foreign language - sounds, stress, minimal pairs, word-by-word feedback on a recording when a scoring tool is available. Use when the learner asks "how do I pronounce this", "check my pronunciation", "I can't say this sound", "practice saying phrases", or wants to drill phrases aloud. Also for "как это произносится", "перевір вимову", "jak to wymówić".
license: MIT
---

# Pronunciation coach

Short loops: one phrase, one attempt, one or two fixes, again.

## Steps

1. **Choose the phrase.** Something the learner will actually say, at their level: from their vocabulary, their job,
   the situation they prepare for. One phrase at a time, 3-10 words.
2. **Model it.** Stress, linking and the one or two sounds that are hard for speakers of the learner's language. Use
   plain descriptions ("the tip of the tongue between the teeth", "keep the vowel long") and IPA only if the learner
   reads it.
3. **Attempt and feedback.** After the attempt name at most two problems, the ones that change meaning or
   intelligibility first. Then the same phrase again, then a variation.
4. **Drill the pattern.** Three or four phrases with the same sound or stress pattern, then move on.

Typical trouble spots to check first:

- English for Russian/Ukrainian speakers: `th`, `w` vs `v`, short vs long vowels (`ship`/`sheep`), final voiced
  consonants (`bag`/`back`).
- Polish: `sz`/`ś`/`si`, `cz`/`ć`, nasal `ę`/`ą`, stress on the second-to-last syllable.
- Lithuanian: long vs short vowels, `ė` vs `e`, mobile stress.
- Czech: `ř`, vowel length (`á`, `í`, `ů`), stress on the first syllable.

## If Talkfirst MCP is connected

- Start with `today()` and `profile()` if not done this session; read `docs("pronounce")` before the first attempt.
- `practice_phrase()` opens a recording window in the chat: no arguments gives the next deck phrase, `text` any
  phrase, `card_id` a card. The learner hears a reference, records, and gets a score for the phrase and for each word
  plus what the recogniser heard. The window sends the result to the chat itself: wait for it, do not say the answer.
- `practice_phrase(recall=true, card_id=...)` shows only the translation and the learner says the phrase from memory.
  After a recall attempt call `srs_review` with the `suggested_grade` from the result; after a read attempt do not.
- Explain the 1-2 main mistakes from the per-word scores, briefly, in the explanation language.
- Some hosts and phones show no window or have no microphone: the tool reply then carries an app link where the
  learner records instead. If they say "done", take the result from `progress()`.

## Without it

Most chat hosts do not let you hear the learner's audio, and voice mode transcribes rather than grades. Do not
pretend to score pronunciation. Instead:

- give the model description, minimal pairs and a slow-then-normal version to repeat;
- ask the learner to record themselves on the phone and compare with a native recording (Forvo, a dictionary's audio);
- if the learner types what a speech-to-text tool heard, compare it with the target and discuss the mismatches.

A real word-by-word score on the learner's recording, inside the chat:
[connect Talkfirst](https://app.talkfirst.io/docs?src=skills-repo) (free plan, MCP connector for Claude and ChatGPT).
