# Wortkiste

A German word trainer for beginners. You add words, and Claude writes a card for each one: the article (der/die/das), the plural, an easy example sentence with an English translation, and a tip.

Live page: https://claude.ai/artifact/D95TwHpzp17kaTQmCey2po

## Practice modes

- **Flashcards**: see the German word, recall its meaning, then flip the card.
- **English → German**: see the English, say the German word with its article, then flip the card.
- **der / die / das**: pick the right article for each noun.
- **Listen**: hear the word read aloud and type what you hear.
- **Type it**: see the English, type the German with its article.
- **Fill the gap**: complete an easy sentence with the missing word.

English → German, Listen, Type it and Fill the gap open for a word once it reaches box 2 in Flashcards.

## How words come back

Each mode keeps its own progress, using boxes 1 to 5.

- A right answer moves a word up one box in that mode. A wrong answer moves it down two boxes (box 5 → 3, box 4 → 2, box 3 or 2 → 1).
- A word in box 1 comes back right away, box 2 after 1 day, box 3 after 3 days, box 4 after 7 days and box 5 after 14 days.
- Every further right answer in box 5 stretches the gap to 30, 60 and then 120 days.
- Words become due at the start of the day, from 4 am, not at the minute you answered them. Late-night practice counts for that night.
- Words you miss come back once at the end of the same round for another try. The retry doesn't change their box.
- A round only holds words that are due. When nothing is due, a mode offers an **extra round** that reviews your words without changing any boxes.
- A word is **mastered** when it reaches box 5 in every mode that applies to it.

In typed answers, one wrong letter in a word of 4 letters or more counts as **Almost**: you see the right spelling and choose **Count it as right** or **Count it as wrong**.

## Daily goal and new words

The top of the Practice tab shows a ring for today's **daily goal** (20 reviews unless you change it) and how many new words you've started today. **New words a day** (10 unless you change it) stops a big lesson from flooding the Due count: the oldest new words come first, the rest wait for later days. Both settings follow you to every device.

## Practice settings

- Practice can be limited to one lesson, **Hard words** (answered wrong last time in any mode, or right less than 60% of the time) or **My own words** (words you added yourself, not from a lesson).
- **Say each card** reads the German word aloud when a card appears. **Speak answers** reads the word and its example sentence after each answer.
- While a round runs, **focus mode** hides the header and tabs so only the card is on screen.

## Stats

The Stats tab shows reviews per day for the last 14 days, how many reviews are due on each of the next 7 days, how often you're right in each mode, and your 10 hardest words.

## Lessons

The Lessons tab holds ready-made A1 lessons by topic, about 20 words each: greetings, about me, family, numbers, time, food, home, daily routine, useful verbs, adjectives and colours, question words, and getting around town. Starting a lesson adds only the words you don't have yet. Once most words in your started lessons reach box 2 in Flashcards, the next lesson is marked "Up next". **Pause** takes a started lesson's words out of practice and the Due count until you press **Resume**; their progress is kept.

## Adding words

Type words in the Add tab, up to 20 at a time, in German, English or Russian. Any form works (Hunden, ging, schöne): Claude saves the **dictionary form** (der Hund, gehen, schön) and says what it changed. You can check and fix each card before saving it, or write a card yourself.

## Your data and backups

Your words and progress are not stored in this repository. They live in the artifact's database on claude.ai, private to your account. If the page is opened outside claude.ai, it falls back to the browser's localStorage.

At the bottom of the Words tab, **Download backup** saves all your words with their progress as a JSON file. **Load backup** brings them back: words in the backup replace the same words in your box, and words that aren't in the backup stay as they are.

## On your iPhone

Open the live page in Safari, tap Share, then **Add to Home Screen**. The repository also has a web app manifest and icons (`manifest.json`, `icons/`) for when the page is served on its own.

## Daily reminder

A scheduled task checks your words once a day and sends a notification to your phone when words are due. It's set up in Claude, not in this repository.

## Files

- `index.html`: the app itself, with HTML, CSS and JavaScript in one file and no build step.
- `lessons.js`: the lesson word lists. Each word is `[word, article, plural, type, english, example_de, example_en, gap, tip]`, and `gap` must appear in `example_de`.
- `manifest.json` and `icons/`: the home screen name and icon.

## Updating the live page

Edit the files, then ask Claude to republish them to the same artifact URL above. The page needs the `db`, `user`, `sample` and `downloads` capabilities.
