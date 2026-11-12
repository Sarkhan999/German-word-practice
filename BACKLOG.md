# Wortkiste backlog

Ideas for future improvements, most important first. Tick an item when it's done.

## Now: small, high value

- [x] **Update README.md**
  - Why: the README still describes the old box rules.
  - How: describe the newer features:
    - words become due from 4 am;
    - a wrong answer drops a word 2 boxes;
    - box 5 gaps grow to 14, 30, 60 and 120 days;
    - missed words come back once in the same round;
    - "Say each card";
    - focus mode while practising;
    - "My own words";
    - dictionary forms and Russian input in the Add tab.
- [x] **Backup: export and import**
  - Why: your words and progress live only in the artifact's database.
  - How: a "Download backup" button that saves all words with their progress as a JSON file, and "Load backup" to bring them back.
- [x] **Forgive small typos**
  - Why: one wrong letter in "Kugelschreiber" shouldn't feel like not knowing the word.
  - How: in `checkType()`, treat an answer 1 letter off (Levenshtein distance 1) as "Almost". Show the right spelling and let the user choose "Count it as right" or "Count it as wrong".
- [ ] **Edit a card while practising**
  - Why: a wrong meaning or example sentence is noticed during practice, not in the Words tab.
  - How: a small "Edit" link on the answer card that opens `editor()` for that word.

## Next: new practice modes

- [ ] **Plural mode**
  - Why: plurals are already stored for every noun but never practised.
  - How: "der Hund → die ___", typed like Type it.
- [ ] **Kasus mode (cases)**
  - Why: articles change with the case, which is the hardest part of A1 grammar.
  - How: pick the right article in an easy sentence, e.g. "Ich sehe ___ Hund." → den. Cover nominative, accusative and dative for der/die/das and ein/eine. Claude writes the sentences when the card is made.
- [ ] **Verb forms mode**
  - Why: knowing "gehen" isn't enough; you need "du gehst" and "er geht".
  - How: store a `forms` field (ich/du/er/wir) for verbs when the card is made, then ask for one form at a time.
- [x] **Reverse flashcards (English → German)**
  - Why: Flashcards only go from German to English today, and speaking needs the other direction.
  - How: a new mode, or a switch in Flashcards, that shows the English and recalls the German with its article.
- [ ] **Speak it (pronunciation)**
  - Why: saying words aloud helps them stick.
  - How: use the browser's speech recognition to check the word you say. Hide the mode where the browser can't do it.

## Later: motivation and insight

- [x] **Daily goal and new-word limit**
  - Why: starting a big lesson can flood the Due count.
  - How: a daily goal (e.g. 20 reviews) with a progress ring, and at most N new words per day (e.g. 5).
- [x] **Stats page**
  - Why: to see progress over weeks, not just today.
  - How: show reviews per day, accuracy per mode, a forecast of words due in the next 7 days, and your 10 hardest words.
- [x] **Daily reminder**
  - Why: the streak only counts if you remember to practise.
  - How: a scheduled message to your phone when words are due.
- [ ] **More lessons (A2)**
  - Why: the built-in lessons stop at A1.
  - How: new lessons on work, health, shopping and travel, plus separable verbs (aufstehen, einkaufen) in `lessons.js`.
- [x] **Add to iPhone home screen**
  - Why: it should open full-screen like an app, with its own icon.
  - How: add a web app manifest and an icon.

## Tech and housekeeping

- [ ] **Automated smoke test**
  - Why: so an update can't break practice without anyone noticing.
  - How: a Playwright script, run by a GitHub Action, that plays one round in every mode on an iPhone profile.
- [ ] **Republish on every merge**
  - Why: the live page is a separate copy and doesn't update when GitHub changes.
  - How: after each merged PR, republish `index.html` and `lessons.js` to the artifact, and add this step to the README.
- [ ] **Split `index.html`**
  - Why: one file gets hard to work in.
  - How: once it passes about 1,500 lines, move the CSS to `style.css` and the code to `app.js`; the artifact can serve several files.
