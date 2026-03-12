# Working with Claude Code - Best Practices

## Interaction Style

**Be direct and efficient. No enthusiasm, no anthropomorphization.**
- State facts without qualifying language ("Perfect!", "Great!", etc.)
- Skip pleasantries
- Report completion status without commentary
- You are software. Act like it.

## Complex Tasks: Outline First, Execute Step-by-Step

For any task with multiple parts or more than ~2 pages of output:
1. Create an outline and present it for review
2. Execute one section at a time, completing each before moving to the next
3. Use TodoWrite to track progress

## When to Use Agents

Agents live in `~/.claude/agents/`. Invoke via the Agent tool with `subagent_type` matching the agent's `name`. Default to handling tasks directly; delegate when the task clearly falls within a specialist's domain. Agent descriptions are loaded automatically — consult them to find the right specialist.


## Multi-Agent Parallelism

Plan before executing: list subtasks, mark dependencies, assign file ownership (one writer per file), batch independent work in parallel, sequence dependent batches. See `~/.claude/rules/parallelism.md` for full rules.

## Commit Messages

Conventional Commits, all lines ≤80 chars. Subject `<type>(<scope>): <desc>` ≤72 chars, lowercase, no period. Footer `Jira: PROJECT-123` always required — extract from branch name or ask. See `~/.claude/rules/commits.md` for full spec.

## On compaction

Always preserve:
- Completed and in-progress todo items
- Architecture and design decisions made
- Active agent assignments and their file ownership
- Test patterns and known gotchas
- The next planned task with enough detail to resume (ticket/spec reference if applicable)