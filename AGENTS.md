# Rhino Plugins — Learning Workspace

This is a personal learning workspace, not a code project. No build, test, lint, or CI config exists yet.

## Structure

- `*.md` files at root are **format specs** that define conventions for workspace documents.
- `GLOSSARY.md`, `MISSION.md`, `RESOURCES.md` (root) and `learning-records/` (numbered files) are created lazily as learning progresses — do not create them proactively.
- Teaching approach and resource grouping philosophy is defined in the `teach` skill (`SKILL.md` in the opencode skill system, referenced by `RESOURCES-FORMAT.md`).

## Important rules

- **Do not create any of the workspace documents** (`GLOSSARY.md`, `MISSION.md`, `RESOURCES.md`, learning records) unless the user explicitly asks or the teaching workflow calls for it. The format specs describe *how* to write them, not to create them now.
- **Do not write code, create projects, or install packages** unless the user asks. This is a learning workspace — no Rhino plugin code exists yet.
- `.gitignore` is the standard `dotnet new gitignore` for Visual Studio/.NET projects (expects `.sln`, `.csproj`, `.vs/`, `bin/`, `obj/`, etc.).

## Commands

None. No package manager, test runner, or build tooling has been set up.
