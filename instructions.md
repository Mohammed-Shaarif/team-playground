## 0. Setup (Once)

1. **Create a shared repo**

   * One of you creates a **public GitHub repository** named `team-playground`.
   * Add a `README.md` with a one-line description.

2. **Invite collaborator**

   * Add the other person as a *collaborator* with write access.

3. **Clone locally**

   * Both clone it to your own machines.

---

## 1. Roles to Pretend

* **You**: “Backend engineer” (even if you don’t write backend code).
* **Friend**: “Frontend engineer.”
* Occasionally swap roles.

You will **alternate acting as “Maintainer”** (person who reviews/merges) and “Contributor” (person who submits PRs).

---

## 2. Learning Sprint Schedule

Below is a 4-session plan (\~1–2 hours each).
Each session builds on the previous one and introduces new Git/GitHub concepts.

---

### **Session 1 – Branching & Pull Requests**

**Goal:** Create feature branches, open PRs, review, merge.

1. Maintainer creates a GitHub Issue: *“Add project introduction to README”*.
2. Contributor:

   * Creates a branch: `feature/readme-intro`.
   * Adds 3–4 lines to `README.md`.
   * Commits and pushes the branch.
   * Opens a Pull Request (PR) linking the issue.
3. Maintainer:

   * Reviews the PR (leave a comment).
   * Requests a minor change (e.g., “Add your name”).
4. Contributor updates the branch, pushes again.
5. Maintainer approves and merges with “Squash & Merge.”
6. Both pull the updated `main`.

---

### **Session 2 – Multiple Features & Merge Conflicts**

**Goal:** Experience conflicts.

1. Create two new issues:

   * *“Add team members section”*
   * *“Add project goals section”*.

2. Each of you works **simultaneously** on a branch that edits the *same lines* of `README.md`.

   * You: `feature/team-members`
   * Friend: `feature/project-goals`

3. Merge one PR first.

4. When the second PR is merged, GitHub flags a conflict.

5. The second contributor resolves the conflict **locally**:

   ```bash
   git fetch origin
   git checkout feature/project-goals
   git merge origin/main
   # resolve conflicts in editor
   git add .
   git commit
   git push
   ```

6. Maintainer merges after fix.

---

### **Session 3 – Issues, Milestones & Labels**

**Goal:** Use GitHub project management features.

1. Maintainer creates a *Milestone* called “v1.0”.
2. Add 3 issues (e.g., “Set up LICENSE,” “Create CONTRIBUTING.md,” “Add .gitignore”).
3. Assign each issue to a person and set labels (`enhancement`, `documentation`, etc.).
4. Work on them in separate branches and PRs, referencing the issues in commit messages:

   ```
   git commit -m "Add MIT License (#5)"
   ```
5. Close the milestone once all issues are merged.

---

### **Session 4 – Advanced Collaboration**

**Goal:** Explore forks, reviews, and release tags.

1. Pretend the repo is **read-only** for contributors.

   * Maintainer changes collaborator permission to *read*.
2. Contributor **forks** the repo, clones their fork, creates a branch, and opens a PR from the fork.
3. Maintainer enables **branch protection** (require PR reviews, require CI to pass).
4. Optionally tag a release:

   ```bash
   git tag -a v1.0 -m "First stable version"
   git push origin v1.0
   ```

---

## Extra Experiments

* **Rebase Practice:** Try `git rebase` to rewrite history and then force-push.
* **Stash/Cherry-Pick:** Create a quick fix while another feature is in progress.
* **GitHub Actions:** Add a simple CI workflow (e.g., lint Markdown) to require checks before merging.

---

## Tips for the Role-Play

* **Switch Maintainer/Contributor roles every session.**
* Keep commits small and meaningful.
* Use GitHub’s **Review** feature: approve, request changes, or comment inline.
* Write descriptive commit messages and PR descriptions.

---

* Branch strategies (`feature/*`, `hotfix/*`)
* PR workflow (open, review, merge)
* Issue tracking, labels, milestones
* Conflict resolution (merge vs. rebase)
* Forks and protected branches
* Release tags and basic CI
