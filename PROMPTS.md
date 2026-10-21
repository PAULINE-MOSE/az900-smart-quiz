# Prompts Used (Prompt Engineering Log)

This file documents the prompts used to build and extend the AZ-900 Smart Quiz Builder. Use them with Claude.ai to grow the question bank safely.

## 1. Question generation prompt

```
You are an expert Azure Fundamentals (AZ-900) instructor writing ORIGINAL
practice questions for beginners.

Topic: [Cloud Concepts | Azure Architecture & Services | Management & Governance]
Subtopic: [e.g. shared responsibility model]
Number of questions: 5

Rules:
- Write original scenarios in your own words. Never reproduce real exam questions.
- Each question has exactly 4 options and exactly 1 correct answer.
- Distractors must be plausible and based on common misconceptions.
- Test understanding of "why", not just recall of a definition.
- Use current Azure names (for example, Microsoft Entra ID).
- Keep each question under 40 words.

Output ONLY a JavaScript array in this exact format:
{t:"cloud|arch|gov", q:"...", o:["...","...","...","..."], a:<index 0-3>, e:"..."}
```

## 2. Explanation prompt

```
For the question below, write a 2-3 sentence explanation that:
1. States why the correct answer is right.
2. Briefly says why each wrong option is wrong or when it WOULD be right.
3. Uses plain language for a beginner.

[paste question and options]
```

## 3. Accuracy review prompt

```
Act as a strict technical reviewer for AZ-900 content. For each question
below, check that (a) exactly one option is correct, (b) the explanation is
factually accurate, (c) service names are current, and (d) the wording is not
copied from any real exam. List any problems and suggest fixes.

[paste questions]
```

## 4. Build prompt (app creation)

```
Build a single-file HTML quiz app: topic selection, one question at a time,
shuffled options, instant correct/incorrect feedback with an explanation,
progress bar, results screen with review of missed questions and a "retry
missed" button, best score saved in localStorage, light/dark mode, mobile
friendly, and a visible "unofficial, not affiliated with Microsoft" banner.
```

## Review process

1. Generate with prompt 1, then refine explanations with prompt 2.
2. Run prompt 3 as a second pass.
3. Manually verify every question against Microsoft Learn before publishing.
4. Test the quiz and confirm every answer key is correct.
