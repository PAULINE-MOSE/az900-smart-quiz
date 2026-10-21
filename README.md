# 🧠 AZ-900 Smart Quiz Builder

> **Unofficial community practice tool.** All questions are original. This project is not affiliated with, endorsed by, or sponsored by Microsoft. It contains no real exam questions and no Microsoft logos.

Built for the **GENERATE Vibe Coding Hackathon: AZ-900 Exam Prep Edition**.
Theme: *"Building Smarter Exam Prep Tools from Our Own Learning Journey."*

🔗 **Live demo:** `https://YOUR-USERNAME.github.io/az900-smart-quiz/`

---

## The problem

When practising for AZ-900, many learners tap through questions, see "Correct" or "Incorrect," and move on. They never find out **why** an answer is right or wrong, so the same mistakes come back on exam day.

## The solution

A lightweight quiz app that gives **instant feedback and a clear explanation for every answer**, organised by the three AZ-900 skill areas:

| Topic | Questions |
|---|---|
| Cloud Concepts | 6 |
| Azure Architecture & Services | 6 |
| Management & Governance | 6 |

## Features

- ✅ Instant green/red feedback on every answer
- 💡 Explanation after each question, covering why the right answer is right and why common wrong answers aren't
- 🗂️ Practise one topic or a mixed set
- 🔀 Shuffled questions and options on every attempt
- 📊 Results screen with percentage score and encouragement
- 🔁 **Review your misses**, then **Retry missed** to re-quiz only the questions you got wrong
- 🏆 Best score per topic, saved in your browser
- 🌗 Automatic light and dark mode
- 📱 Responsive and mobile-friendly
- 🏷️ "Unofficial" disclaimer shown on every screen

## How it works

The app is a single self-contained `index.html` file with no build step, no dependencies and no backend. Questions live in one JavaScript array, so adding content is simple:

```js
{
  t: "cloud",                                   // topic: cloud | arch | gov
  q: "Question text?",
  o: ["Option A", "Option B", "Option C", "Option D"],
  a: 1,                                         // index of correct option (starts at 0)
  e: "Why the answer is right, and why the others aren't."
}
```

Options are shuffled at runtime, and the correct answer is tracked by position in the original array, so the order you write doesn't matter.

## Run it locally

1. Download or clone this repo.
2. Open `index.html` in any browser. No server needed.

## Deploy with GitHub Pages

1. Push these files to a public repo.
2. Go to **Settings → Pages**.
3. Set **Source** to *Deploy from a branch*, branch `main`, folder `/ (root)`.
4. Your site appears at `https://YOUR-USERNAME.github.io/REPO-NAME/` within a couple of minutes.

## Tools and prompt engineering

- **Claude.ai**: prompt design, question and explanation drafting, and building the app
- Prompts and the review process are documented in [`PROMPTS.md`](PROMPTS.md)

## Accuracy note

Questions were written from my own understanding of the AZ-900 skills outline and reviewed against Microsoft Learn. Azure service names and features change, so always confirm against the official [Microsoft Learn AZ-900 study guide](https://learn.microsoft.com/credentials/certifications/azure-fundamentals/).

## Roadmap

- 📚 Grow the bank to 100+ questions across all AZ-900 objectives
- ⏱️ Timed exam-simulation mode
- 🤖 AI "explain it differently" button powered by Claude
- 🧩 Supabase backend for shared leaderboards and learner progress tracking
- 🎓 Reuse the same engine for AI-900, AZ-104 and other certifications by swapping the question set

## Who it's for

- First-time AZ-900 candidates who want to understand concepts, not memorise answers
- Study groups and cohorts who need a free, shareable practice tool
- Learners who prefer short, focused sessions on a single topic

## Contributing

Question ideas and fixes are welcome. Please write original questions only. Do not submit real exam content.

## License

MIT, see [`LICENSE`](LICENSE).
