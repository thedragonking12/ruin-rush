# AGENTS.md

Ground rules for every AI that works in this repo. Read this file before starting any task.

## The team

| Role | Who | What they do |
| --- | --- | --- |
| Manager | External manager agent | Creates issues, assigns them by role, tracks progress, checks that merged work matches the plan. |
| Coder | Claude | Builds features and fixes bugs in a branch and opens a pull request. |
| Researcher | Gemini | Investigates a question and saves the findings in `research/`. |
| Reviewer | ChatGPT | Reviews pull requests and writes the result in `reviews/` and as a PR comment. |
| Helper | GitHub Copilot | Small fixes, pull request descriptions and cleanup, on issues the manager gives it. Can back up the coder. |
| Owner | thedragonking12 | Makes the final call and does the merge. |

Edit the "Who" column as the team changes. One AI can hold more than one role, but should not review its own code.

## How work flows

1. **Manager** opens an issue using a template in `.github/ISSUE_TEMPLATE/` and adds one role label: `role:coding`, `role:research` or `role:review`.
2. The assigned AI comments "Taking this" on the issue so nobody else starts the same task.
3. **Coder** works on a branch named `feature/<short-name>` or `fix/<short-name>`, then opens a pull request that links the issue (`Closes #12`).
4. **Researcher** saves findings as `research/<topic>.md` and posts the link on the issue.
5. **Reviewer** reads the pull request, tests the change where possible, and writes a short result in `reviews/pr-<number>.md`. The verdict is one of: approve, request changes, or blocked.
6. **Owner** merges. Nobody pushes straight to `main`.

## Rules for everyone

- Work only on the issue you were given. If you find something else, open a new issue instead of fixing it quietly.
- Never commit secrets, API keys, tokens or personal data.
- Keep pull requests small. One issue, one pull request.
- Write down what you decided and why, in the issue or in `docs/`. The next AI starts with no memory of your work.
- If an instruction is unclear or two instructions conflict, stop and ask on the issue. Do not guess.
- Say plainly what you did not test or could not finish.

## Rules for the coder

- `index.html` must stay a single self-contained file that opens by double-clicking it. No build step and no external code libraries.
- The game has to stay playable at phone width and with keyboard and touch input.
- Do not add tracking, ads or network requests.
- Before opening a pull request, run the game once and check that it starts, that a run ends in a crash screen, and that restart works.

## Rules for the researcher

- Give every claim a source link. Mark anything you could not verify as unverified.
- Start each note with a three-line summary, then the detail.
- Do not paste long passages from sources. Summarize in your own words.

## Rules for the reviewer

Check, in order:

1. Does the change do what the issue asked, and nothing more?
2. Does the game still start, run, crash and restart correctly?
3. Does it work with keyboard and with touch, at phone width?
4. Is anything unsafe, such as secrets, new network calls or unexpected files?
5. Is the code readable enough for the next AI to change?

## Labels

- `role:coding`, `role:research`, `role:review`
- `status:blocked`, `status:needs-owner`
- `type:bug`, `type:feature`, `type:docs`
