# Wortkiste

A German word trainer for beginners. You add words, and Claude writes a card for each one: the article (der/die/das), the plural, an easy example sentence with an English translation, and a tip.

Live page: https://claude.ai/artifact/D95TwHpzp17kaTQmCey2po

## Practice modes

- **Flashcards**: see the German word, recall its meaning, then flip the card.
- **der / die / das**: pick the right article for each noun.
- **Type it**: see the English, type the German with its article.
- **Fill the gap**: complete an easy sentence with the missing word.

Each mode keeps its own progress, using boxes 1 to 5. Type it and Fill the gap open for a word once it reaches box 2 in Flashcards.

## Files

- `index.html`: the whole app, with HTML, CSS and JavaScript in one file and no build step.

## Your data

Your words and progress are not stored in this file. They live in the artifact's database on claude.ai, private to your account. If the page is opened outside claude.ai, it falls back to the browser's localStorage.

## Updating the live page

Edit `index.html`, then ask Claude to republish it to the same artifact URL above.
