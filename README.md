# Wortkiste

A German word trainer for beginners. You add words, and Claude writes a card for each one: the article (der/die/das), the plural, an easy example sentence with an English translation, and a tip.

Live page: https://claude.ai/artifact/D95TwHpzp17kaTQmCey2po

## Practice modes

- **Flashcards**: see the German word, recall its meaning, then flip the card.
- **der / die / das**: pick the right article for each noun.
- **Listen**: hear the word read aloud and type what you hear.
- **Type it**: see the English, type the German with its article.
- **Fill the gap**: complete an easy sentence with the missing word.

Each mode keeps its own progress, using boxes 1 to 5. A word in box 1 comes back right away, box 2 after 1 day, box 3 after 3 days, box 4 after 7 days and box 5 after 14 days. Listen, Type it and Fill the gap open for a word once it reaches box 2 in Flashcards.

A round only holds words that are due. When nothing is due, a mode offers an **extra round** that reviews your words without changing any boxes.

After each answer the app says the word, then its example sentence, in German. The **Speak answers** switch on the Practice tab turns this off.

Practice can be limited to one lesson or to **Hard words**: words answered wrong last time in any mode, or right less than 60% of the time. The Words tab filters by article, lesson, progress and difficulty.

## Lessons

The Lessons tab holds ready-made A1 lessons by topic, about 20 words each: greetings, about me, family, numbers, time, food, home, daily routine, useful verbs, adjectives and colours, question words, and getting around town. Starting a lesson adds only the words you don't have yet. Once most words in your started lessons reach box 2 in Flashcards, the next lesson is marked "Up next". The Practice tab can be limited to one lesson. **Pause** takes a started lesson's words out of practice and the Due count until you press **Resume**; their progress is kept.

## Files

- `index.html`: the app itself, with HTML, CSS and JavaScript in one file and no build step.
- `lessons.js`: the lesson word lists. Each word is `[word, article, plural, type, english, example_de, example_en, gap, tip]`, and `gap` must appear in `example_de`.

## Your data

Your words and progress are not stored in this file. They live in the artifact's database on claude.ai, private to your account. If the page is opened outside claude.ai, it falls back to the browser's localStorage.

## Updating the live page

Edit `index.html`, then ask Claude to republish it to the same artifact URL above.
