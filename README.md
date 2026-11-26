# Calibrate SSAT Reading

An English-language Agent Skill for tutors and families creating and grading SSAT Upper Level reading practice. Its central question is simple: **When two choices look plausible, which word, sentence, or structural feature makes one answer stronger?**

## Try a first session

After installing the skill, ask:

> Use calibrate-ssat-reading to create a 20-question mixed reading set. Choose four fresh excerpts, verify their sources, and give me the student paper first. Hold the answer key until I finish independent review.

The default set includes fiction, science or nature writing, a humanities argument, and poetry. Each passage has five questions with choices A–E. The suggested practice schedule is **22 minutes for the first pass and 5 minutes for independent review**. These are training settings. The skill reports raw practice results and makes no claim of official score equivalence.

Submit each answer with a confidence rating: **H** for high, **M** for medium, or **L** for low. For example, `1E-M(D)` means “I chose E with medium confidence and also considered D.” To change an answer during review, state the new choice explicitly and identify the passage evidence that changed your mind. The grader preserves the first-pass result so you can see what review actually changed.

## What the skill checks

- **Passages.** Verify the edition and excerpt boundaries, select continuous text, and identify at least three distinct inferences the excerpt supports. Prose selections typically run 250–550 words. Verifying a new source requires access to its full text.
- **Questions.** Record the evidence for the key, explain why each distractor is attractive, and identify the precise defect in the strongest rival. Revise or withdraw a question when two choices remain defensible.
- **Feedback.** Explain the student's actual choice, flag high-confidence errors, and test the same reading distinction with fresh material. Record timing and review gains only when the student supplies the relevant data.

To audit an existing question, provide the passage, stem, and all five choices, then ask:

> Solve this item before looking at my key. Quote the evidence for your answer, make the strongest case for its closest rival, and tell me whether the passage resolves the distinction.

## Installation

Use a folder named `calibrate-ssat-reading` with `SKILL.md` directly inside it. If you use GitHub's **Download ZIP**, extract the archive and rename the extracted folder if GitHub added a branch suffix. Keep the `references/` folder alongside `SKILL.md`.

| Platform | Where to put the skill |
| --- | --- |
| OpenAI Codex | Copy the folder into the project's `.agents/skills/` directory. |
| GitHub Copilot with Agent Skills support | Copy the folder into `.github/skills/` or `.agents/skills/`. Codex and Copilot can share the same project copy. |
| Claude Code | Copy the folder into the project's `.claude/skills/` directory. |
| Claude web | Zip the folder so the archive contains `calibrate-ssat-reading/SKILL.md`. Open **Customize → Skills**, upload the ZIP, and enable the skill. |

## Repository guide

| File | Purpose |
| --- | --- |
| [SKILL.md](SKILL.md) | The complete workflow for selecting passages, writing questions, reviewing answers, and grading. |
| [review-templates.md](references/review-templates.md) | Passage and item records, an independent review table, and a grading summary. |
| [project-calibration.md](references/project-calibration.md) | A historical record. |
| [openai.yaml](agents/openai.yaml) | OpenAI display settings and a default prompt. |

**Before publishing a public fork**, review the historical calibration file. It contains learner-specific scores and confidence breakdowns. For a general-purpose edition, replace its contents with a blank tracking template at the same path. The passage-selection and grading workflow can be used with a new learner from the first session.
