# Ruin Rush

An endless three-lane runner through jungle ruins. Switch lanes, jump low walls, slide under arches and collect gold while the speed keeps climbing.

**Play it:** https://thedragonking12.github.io/ruin-rush/

## Controls

| Action | Keyboard | Touch |
| --- | --- | --- |
| Change lane | Left / Right, or A / D | Swipe left / right |
| Jump | Up, W or Space | Swipe up, or tap |
| Slide | Down or S | Swipe down |
| Pause | P or Esc | Pause button |

## How the game works

- Low walls need a jump. Arches with red-striped beams need a slide. Tall blocks mean you switch lanes.
- Every row of obstacles leaves at least one passable lane.
- Score is distance in metres plus 10 for each gold coin. The best score is saved in the browser.

## Project layout

```
index.html        The whole game (HTML, CSS, JavaScript). Served by GitHub Pages.
AGENTS.md         Roles, rules and handoff process for the AI team.
research/         Research notes written by the research AI, one file per topic.
reviews/          Review notes written by the review AI, one file per pull request.
docs/             Design decisions and anything the team needs to remember.
.github/          Issue templates and the pull request template.
```

## Working on this repo

This project is built by a small team of AIs coordinated by a manager agent. Read [AGENTS.md](AGENTS.md) before making changes.
