# git-RescueQuest

An interactive browser game that teaches developers how to fix common Git accidents. Built with the GitHub Copilot cloud agent for **MLH Global Hack Week: Hacktoberfest**.

## Live demo

**Play in your browser:** [https://sayemr0018.github.io/git-RescueQuest/](https://sayemr0018.github.io/git-RescueQuest/)

## How it works

You play through 5 incident response scenarios on release day. Each level presents a broken Git state and three terminal commands. Picking a command shows simulated terminal output and explains why that choice fixes or worsens the repository state.

### Scenarios covered

| Level | Incident | Recovery command | Why it works |
| :--- | :--- | :--- | :--- |
| **1** | Committed a `.env` secret locally before pushing | `git reset --soft HEAD~1` | Undoes the commit while keeping file changes staged so you can untrack `.env`. |
| **2** | Made new commits while in a detached `HEAD` state | `git switch -c rescue-branch` | Creates a new named branch pointing at your current commit so the work is not lost. |
| **3** | Lost a critical commit after running `git reset --hard` | `git reflog` + `git checkout <hash>` | Reads Git's local reference log to find the dangling commit hash and restore it. |
| **4** | Pushed a broken commit to a shared `main` branch | `git revert HEAD` | Creates a new inverse commit that undoes the changes without rewriting shared history. |
| **5** | Need a single bugfix commit from another branch | `git cherry-pick <hash>` | Applies only the specified commit onto your current branch without merging unready work. |

## Features

- **Zero dependencies:** Written in vanilla HTML5, CSS3, and JavaScript inside a single `index.html` file.
- **XP and repository health tracking:** Tracks your score and repository stability across all 5 levels.
- **Instant terminal explanations:** Explains the exact mechanics of both right and wrong Git commands.
- **End-of-game reference card:** Displays your developer rank and a command cheat sheet at the end of a run.

## Project structure

```text
git-RescueQuest/
├── index.html   # Complete game UI, styles, scenario state, and logic
└── README.md    # Project documentation
```

## Run locally

No build step or package manager is required. Clone the repository and open `index.html` in any browser:

```bash
git clone [https://github.com/sayemr0018/git-RescueQuest.git](https://github.com/sayemr0018/git-RescueQuest.git)
cd git-RescueQuest
start index.html
```

## Built with GitHub Copilot

Generated using the **GitHub Copilot cloud agent** during repository creation. Copilot was prompted to build a single-file, zero-dependency educational Git game in `index.html` so it deploys straight from the `main` branch via **GitHub Pages**.
