# Qoder integration

Generate subagents with `./scripts/convert.sh --tool qoder` and install them with `./scripts/install.sh --tool qoder`. The default destination is `~/.qoder/agents/`; use `--path "$PWD/.qoder/agents"` for a project, or set `QODER_AGENTS_DIR`. The installer supports `--division`, `--agent`, and `--agents-file` filters.

Generated files are Markdown with the `name` and `description` Qoder requires, the agent prompt as the body, and — when the source agent declares a `tools:` allow-list — the same list under Qoder's spellings (Qoder names its tools the way Claude Code does: `Bash`, `Edit`, `Write`, `Glob`, `Grep`, `Read`, `WebFetch`, `WebSearch`; `MultiEdit` folds into `Edit` and `Task` becomes `Agent`). An agent without a source allow-list omits `tools:` and keeps Qoder's default available set.

Two Qoder-side notes:

- Project-level agents under `<project>/.qoder/agents/` are only picked up when the Qoder CLI trusts the project folder ([loading docs](https://docs.qoder.com/cli/troubleshoot-loading)).
- Re-running the installer replaces generated agents with the same slug; a hand-written agent file of the same name in the destination is overwritten too.

See the [Qoder subagent documentation](https://docs.qoder.com/extensions/subagent) (IDE) and [CLI subagents](https://docs.qoder.com/cli/subagent).
