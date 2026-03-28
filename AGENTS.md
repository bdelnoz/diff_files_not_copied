<!--
Document : AGENTS.md
Auteur : Bruno DELNOZ
Email : bruno.delnoz@protonmail.com
Version : v3.3.0
Date : 2026-03-28 01:35
-->
# AGENTS.md

## 🔴 CRITICAL GIT WORKFLOW (HIGHEST PRIORITY)

- Every task MUST start from a clean and up-to-date `origin/main`.

- Before applying any change:
  - fetch origin
  - ensure working state is aligned with latest `origin/main`

- Before creating a PR:
  - fetch origin
  - rebase or reset onto latest `origin/main`
  - verify that HEAD strictly matches the latest `origin/main` base

- NEVER reuse a stale worktree, outdated branch, or obsolete branch state.
- NEVER continue working on a new change from the same branch after a PR has been merged.

- After a PR is merged:
  - the previous working branch/state MUST be considered obsolete
  - a NEW branch MUST be created from latest `origin/main`

- If the current environment is uncertain, stale, or diverged:
  - force refresh from `origin/main` before proceeding

- Avoid creating PRs from stale, diverged, reused, or outdated branches.

- Prefer:
  - one coherent task per branch
  - one fresh branch per merged PR

- Before proposing any git command that modifies history or state, explicitly prefer the safest non-destructive path unless the user requested a destructive action.

## Active instruction set

- This `AGENTS.md` file is the only active instruction source for this repository.
- Treat `AGENTS.md` as the only valid active rule set.
- Do not combine these repository rules with older external rule files or legacy rule sets.
- If this `AGENTS.md` file is updated later, the newest complete version becomes the only valid active instruction set for this repository.
- Do not summarize these repository rules.
- Do not reinterpret these repository rules.
- Apply these repository rules as written.
- Do not request, require, or depend on any external rule file when this `AGENTS.md` is present.

## Language and communication rules

- Interactive chat exchanges with the user MUST be written in French by default.
- Any AI agent working in this repository MUST reply to the user in French in direct chat interactions, unless the user explicitly requests another language for the conversation.
- All repository deliverables and artifacts MUST be written in English by default.
- This includes, but is not limited to: source code deliverables, Markdown files, documentation files, README files, CHANGELOG files, INSTALL files, WHY files, comments intended for repository maintainers, commit messages, pull request titles, and pull request descriptions.
- Do not apply chat-language rules to repository files or repository deliverables.
- Only switch repository deliverables or artifacts to French if the user explicitly requests French for those deliverables.
- Technical terms, code, commands, logs, error messages, protocol names, API names, commit labels, and standard engineering vocabulary may remain in English when appropriate.

## General execution behavior

- Follow the user request directly.
- Always communicate with the user in French in direct chat interactions unless the user explicitly requests another language.
- For script work, provide the **full complete script** immediately, even for a tiny modification.
- Do not provide partial patches instead of the full script when the request is about script generation or script correction.
- Do not simplify existing scripts.
- Do not remove existing features.
- Do not condense existing code.
- Do not reduce the number of lines compared with the previous version of a script.
- If the requested modification explicitly asks to simplify, remove, or condense existing content, ask for confirmation before producing that reduced version.
- When possible, provide generated content as downloadable files first; after that, ask whether the user also wants the content displayed in a Markdown box.
- When the user asks to modify a file, provide the full complete updated file, not only a partial diff or isolated patch, unless the user explicitly asks for a diff.
- Do not leave placeholders such as TODO, FIXME, <value_here>, or "adapt as needed" in deliverables unless the user explicitly requests a template.
- Prefer ready-to-use outputs over partially prepared outputs.
- Never remove existing comments, metadata, changelog entries, options, safety checks, or documentation sections unless the user explicitly requests their removal.
- Do not rename existing files, functions, variables, directories, services, or commands unless the user explicitly requests it.
- Do not invent tests, executions, validations, results, metrics, dates, environments, or completed actions that did not actually occur.
- If something was not executed or verified, state it explicitly.
- Clearly distinguish between:
  - what is already done
  - what is proposed
  - what still requires execution or validation
- Do not silently reformat, reorder, reorganize, or normalize existing content unless the user explicitly requests such restructuring.
- Prefer outputs that are directly usable, copy-paste ready, and execution-ready.
- Avoid abstract explanations when the user asked for an operational result.
- Do not ask for confirmation when the user clearly requested an immediate modification or generation.
- Execute the requested work directly unless a real ambiguity blocks correctness.

### Non-destructive update guards (mandatory)

- For existing files, update in-place and preserve prior content unless explicit removal is requested by the user.
- Full file rewrites of existing files are forbidden unless the user explicitly asks for a complete rewrite.
- For `CHANGELOG.md`, updates are append-only: do not delete, compress, summarize, or rewrite existing historical entries.
- Any change that removes existing `CHANGELOG.md` lines is forbidden unless explicitly requested by the user.
- Before commit, run a focused diff check on `CHANGELOG.md`; if removed lines are detected, stop and fix before continuing.

### Mandatory companion updates for script-related tasks

- Any modification to a script file automatically requires companion updates in the same task.
- Unless the user explicitly forbids it, every script-related change MUST also update, create, or complete as needed:
  - the script internal version
  - the script internal date
  - the script internal changelog
  - `./README.md`
  - `./CHANGELOG.md`
  - `./INSTALL.md`
  - `./WHY.md`
- A script-related task is NOT complete until these companion files have been checked and updated when applicable.
- Do not treat documentation updates as optional when a script changes.
- If a related mandatory documentation file does not exist, create it automatically.
- If a related mandatory documentation file already exists, update it in place.
- If a script is modified, do not stop after editing only the script when related repository documentation is missing, outdated, or incomplete.
- When a script changes, repository deliverables must remain synchronized with the script in the same task.

### Mandatory version bump and release metadata updates

- Any modification to an existing script file MUST trigger a version bump in the same task.
- Do not leave the script version unchanged after a real script modification.
- The script internal version, internal date, and internal changelog entry MUST be updated together in the same task.
- If the repository contains companion documentation tied to the script version, that documentation MUST also be synchronized in the same task.
- A script-related task is NOT complete until the version bump has been applied wherever required by this `AGENTS.md`.
- If the user explicitly requests no version bump, follow the user request; otherwise, version bumping is mandatory.
- If a script change is only cosmetic and the user explicitly forbids version changes, state that constraint clearly; otherwise, do not skip the version bump.
- Never silently keep the previous version number after modifying script logic, options, behavior, metadata, or documentation tied to that script.

## Secrets and sensitive material

- Never place secrets, passwords, certificates, tokens, or similar sensitive values directly in versioned code.
- If a script needs secrets, use a local file at `./.secrets`.
- Ensure `./.secrets` is covered by `.gitignore`.
- Do not push secret material to git.

## Script authoring rules

### Internal comments

- Comment each block and each section as much as possible to explain the internal logic.

### Mandatory header for executable scripts

Every executable script must start with a header containing at minimum:

- Full path and script name
- Author name
- Email
- Target usage / short purpose
- Version
- Date
- Changelog

### Author identity

Use the following values unless the user explicitly overrides them:

- Author: **Bruno DELNOZ**
- Email: **bruno.delnoz@protonmail.com**

### Versioning

- All generated scripts must be versioned and dated, even for a minor modification.
- The first version must start at **v1.0** or **v1.0.0**.
- Increment the version every time a script is produced again.
- The changelog must be updated every time.
- Do not add changelog entries that merely say new scripting rules were applied.

### Version bump execution rules

- Version bumping is mandatory for every script modification unless the user explicitly forbids it.
- Updating the script content without updating its version metadata is forbidden.
- Updating the script version without updating the script date and changelog is forbidden.
- If a script is modified, the agent MUST update the version, date, and changelog before considering the task finished.
- Treat version bumping as part of the required implementation, not as an optional follow-up step.

### Changelog rules

- Keep the complete version history in the script.
- No version entry may be omitted.
- `--changelog` must always exist.
- The changelog display should use Markdown formatting when possible.
- If a separate `CHANGELOG.md` file exists, it may hold the detailed history while the script keeps at least every version, its date, and a short explanation.

### Progress display

- When applicable, scripts must display execution progress.
- For multi-step execution, display the current step with its name and index, for example `Scan du disque (1/56)`.

## Mandatory CLI behavior for scripts

### Help

- A help block is mandatory.
- If no argument is provided, display help by default.
- `--help` must document every usage, every option, every argument, default values, all possible values, and several clear examples.

### Required options

Include these options whenever applicable and keep their behavior aligned with this `AGENTS.md`:

- `--help` / `-h`
- `--exec` / `-exe`
- `--stop` / `-st` when applicable
- `--prerequis` / `-pr`
- `--install` / `-i`
- `--simulate` / `-s`
- `--changelog` / `-ch`
- `--purge` / `-pu`

### Defaults

- Define default values when arguments are omitted.

### Simulate mode

- `--simulate` is a CLI option.
- `--simulate` is inactive by default.
- The presence of `--simulate` alone activates dry-run mode.
- It must be callable directly, for example: `script.sh --simulate`.
- Do not require `true` or `false` values for `--simulate`.
- In simulate mode, reading, analysis, and logging remain active.
- Sensitive actions and system modifications must not execute for real while `--simulate` is present.

### Prerequisites

- Support prerequisite verification before execution.
- `--prerequis` must list prerequisites and report each one as satisfied or missing.
- If something is missing, handle it cleanly and propose `--install`.
- A skip path may exist when appropriate.

## Runtime output, logs, and artifacts

### Console explanations

- For each script execution, explain each step clearly in the console.
- Mirror the same logic in comments and in logs.

### Post-execution summary

- After execution, print a numbered list of all actions performed.

### Logs

- Create a `./logs` directory next to the script if it does not already exist.
- Write detailed logs there.
- Log filename pattern must follow the repository rule form defined in this `AGENTS.md`:
  - `./logs/log.<script_name>.<full_timestamp>.<script_version>.log`

### Results

- Create a `./results` directory next to the script if it does not already exist.
- Put generated content there.
- Generated filenames must be tied to the script name and version.
- Example: `./results/<other_name>.<script_name>.vX.X.txt`
- The destination folder for results must be overridable with `--dest_dir`.

## Sudo and ready-to-use behavior

- Prefer scripts that are ready to use immediately.
- Always put `sudo` inside the script.
- Do not require the user to run `sudo ./script.sh`.
- Prefer zero external sudo.

## Documentation generation rules

### Automatic files

For script projects, on first creation generate without asking:

- `./README.md`
- `./CHANGELOG.md`
- `./INSTALL.md`
- `./WHY.md`

### Major version updates

- On a major version bump (e.g. `3.2.0` → `4.0.0`), ask the user before updating `README.md` and `CHANGELOG.md`.

### Update behavior

- Documentation maintenance is mandatory on script-related tasks, not optional.
- For any script modification, check `./README.md`, `./CHANGELOG.md`, `./INSTALL.md`, and `./WHY.md` in the same task and update them when applicable.
- Do not stop after updating only the script when companion documentation is missing, stale, incomplete, or inconsistent with the script.
- If one of the mandatory documentation files does not exist, create it automatically.
- Never delete or compress existing documentation files.
- If sections are missing, complete them automatically.
- Ensure generated `.md` files include:
  - full script name
  - precise date and time of last generation or modification
  - script version
  - authors and contacts

### CHANGELOG.md content

- `CHANGELOG.md` must exist in `./`.
- It must contain the version number, exact date and time, author name, and the full list of changes with a short description for each point.
- Keep the complete history of all versions.
- Never remove older versions.

## Metadata rules for documents and artifacts

### Executable non-shell scripts

- Executable scripts written in other languages (`.py`, `.js`, `.java`, `.ps1`, etc.) must carry the same header information as shell scripts.
- Only the comment syntax changes with the language.
- Place the header at the beginning of the file, after the shebang if applicable.
- Apply the same versioning and changelog rules as for shell scripts.

### Markdown documents

- A standalone `.md` document must start with a metadata block before the first title.
- The metadata must contain at minimum: document name or title, author, email, version, date and time.
- Use the following exact repository HTML comment format:

```md
<!--
Document : <Full document name>
Auteur : Bruno DELNOZ
Email : bruno.delnoz@protonmail.com
Version : vX.X.X
Date : YYYY-MM-DD HH:MM
-->
# <Document title>
```

- No changelog is required in a standalone `.md` document.
- If a `.md` file is generated as script documentation, it must also follow the documentation rules above.

### Text documents

- A standalone `.txt` document must start with a metadata block.
- The metadata must contain at minimum: document name or title, author, email, version, date and time.
- No changelog is required in a standalone `.txt` document.

## Repository expectations for Codex and Claude Code

- Treat this file as repository-wide instructions.
- Apply these rules before proposing code changes, reviews, or generated artifacts.
- When working inside this repository, prefer compliance with this file over generic habits.
- Keep outputs strict, direct, and operational.
