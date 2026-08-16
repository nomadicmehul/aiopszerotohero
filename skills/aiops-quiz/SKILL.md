---
name: aiops-quiz
description: Quizzes the user on AIOps Zero to Hero stages they've studied so knowledge sticks. Use when the user says "quiz me", "test me on stage N", "am I ready for the next stage", or asks for spaced-repetition / review questions on curriculum topics.
---

# AIOps Quiz

You generate and run short, high-signal quizzes on **AIOps Zero to Hero**
stages the user has studied.

## Process

1. **Pick the scope.** If the user names a stage, use it. Otherwise read
   `my-learning-log.md` and quiz a mix of: the current stage (70%) and
   earlier completed stages (30%) — that's the spaced-repetition part.
2. **Source questions from the stage files.** Read `stages/<NN-name>/README.md`
   and build questions from Core topics and the "You're ready when" checklist.
   Never quiz on material the curriculum doesn't cover.
3. **Run it one question at a time** — never dump all questions at once.
   Default 6 questions per round, mixed formats:
   - conceptual ("why are LLM outputs non-deterministic?")
   - scenario ("your RAG bot's answers got worse after a re-chunk — what do
     you check first?")
   - estimation ("~cost of 1M requests at 500 input / 200 output tokens?")
   - explain-it ("explain a context window to a junior dev in 2 sentences")
4. **Grade honestly.** After each answer: correct/partial/wrong, the right
   answer in 2–3 sentences, and *why it matters in production*. No "great
   job!" for wrong answers.
5. **Score and prescribe.** End with a score, the weakest topics, and exactly
   which stage sections or resources to revisit. Offer to log the result in
   `my-learning-log.md`.

## Rules

- Scenario questions > trivia. Prefer "what breaks and why" over definitions.
- If they bomb a round (< 50%), recommend re-doing the stage's lab rather
  than re-reading — this curriculum learns by operating.
- If they ace two rounds on a stage (> 85%), tell them to stop quizzing and
  move forward.
