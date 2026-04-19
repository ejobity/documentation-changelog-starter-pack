# documentation-changelog-starter-pack
Laravel developer workflow for automated versioning, changelog generation, documentation updates, and AI-assisted task completion.  Project context:  Laravel backend Flux UI frontend Uses VS Code AI tools: Copilot, Codex, Claude  Your task is to INSTALL, VERIFY, and COMPLETE the setup using the existing files in the repository.

## What’s inside:

package.json
commitlint.config.mjs
cliff.toml
VERSION
CHANGELOG.md
.husky hooks
scripts/ for version bump, task logging, and docs stamp
.vscode/tasks.json
docs/ with VitePress config and starter docs pages

## Best way to use it:

Extract the zip into a temporary folder.
Copy the files into your Laravel repo, merging carefully with existing files.
Paste the Copilot prompt into VS Code AI chat and let it install/adjust everything for your actual repo state.

## Important note:

I included git-cliff config, but not the binary itself. You’ll still need to install git-cliff on your machine separately.
The package versions in the starter pack are reasonable templates, but your AI should reconcile them with your current repo before finalizing.

A good next commit message for this setup would be:

chore(devx): add automated versioning changelog and docs workflow

## COPY and Paste this into VSCODE AI
You are setting up a Laravel developer workflow for automated versioning, changelog generation, documentation updates, and AI-assisted task completion.

Project context:

* Laravel backend
* Flux UI frontend
* Uses VS Code
* AI tools: Copilot, Codex, Claude

Your task is to INSTALL, VERIFY, and COMPLETE the setup using the existing repository files.

---

## Step 1: Install dependencies

Run:

* npm install
* npx husky init

Ensure husky is properly initialized.

---

## Step 2: Setup commitlint

* Ensure commitlint.config.mjs is valid
* Create/verify commit hook:

.husky/commit-msg:
npx --no -- commitlint --edit "$1"

---

## Step 3: Verify scripts

Ensure these scripts work:

* npm run changelog:update
* npm run docs:dev
* npm run commitlint

Fix anything missing or broken.

---

## Step 4: Install git-cliff

If not installed:

* Install git-cliff for this system
* Verify:
  git-cliff --version

---

## Step 5: Upgrade scripts (IMPORTANT)

Replace placeholder scripts in /scripts with production-ready logic:

1. bump-version.mjs:

* Read VERSION file
* Apply semver bump (patch, minor, major)
* Write updated version

2. task-complete.mjs:

* Log entry to docs/releases/task-log.md
* Include:

  * timestamp
  * version
  * git commit hash
  * short message

3. docs-stamp.mjs:

* Update docs/index.md
* Add "Last updated" timestamp

---

## Step 6: Improve VS Code Tasks

Update .vscode/tasks.json to include:

* Tests: Laravel
* Docs: Dev Server
* Changelog: Update
* Version: Patch
* Version: Minor
* Version: Major
* Task: Complete (with prompt input)
* Release: Patch Workflow (sequence)
* Release: Minor Workflow (sequence)

---

## Step 7: Setup documentation system

* Ensure /docs structure exists
* Ensure VitePress config works
* Verify:
  npm run docs:dev

---

## Step 8: Enforce AI workflow rules

Create/update AI instructions file:

When completing ANY task:

1. Update relevant docs in /docs
2. Suggest Conventional Commit
3. Suggest version bump (patch/minor/major)
4. Add changelog entry
5. Log task completion
6. Keep Laravel architecture clean:

   * Services for logic
   * Form Requests for validation
   * Enums for statuses

---

## Step 9: Validate everything

Run:

* npm run changelog:update
* npm run docs:dev
* php artisan test

Fix any issues.

---

## Step 10: Output required

Return:

* Summary of setup
* What was fixed/improved
* Any missing optimizations
* Suggested next steps

Do NOT skip steps. Fully complete the setup.

## END


## Important Upgrade (Highly Recommended)

After you run this once, create a reusable prompt file:

/.prompts/task-completion.md

Put this inside:

After completing a task:

1. summarize the change (3-6 bullets)
2. list changed files
3. update docs in /docs
4. suggest Conventional Commit
5. suggest version bump
6. write changelog entry
7. log task completion

👉 Then you can just type in VS Code:

"use task-completion prompt"
