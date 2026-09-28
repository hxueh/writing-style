# Writing style

A compact, self-contained skill for applying one writing voice across ordinary replies, explanations, work documents, and personal writing. The voice stays recognizable while the format follows the task.

## Install in Codex

Run from this directory to make the skill available across projects:

```sh
mkdir -p "$HOME/.agents/skills"
ln -s "$PWD" "$HOME/.agents/skills/writing-style"
```

The link command deliberately fails if the destination already exists. Inspect that installation before replacing it. Keep this checkout in place, or copy the directory instead. Codex supports [user-scoped skills and symlinked folders](https://learn.chatgpt.com/docs/build-skills).

## Apply to every response

Automatic skill selection is conditional. To request this style for all prose, add the following to your existing global `AGENTS.md` in your Codex home (`$CODEX_HOME`, or `~/.codex` by default). Preserve the instructions already there. If `AGENTS.override.md` exists, that file takes precedence at the global level. See [global instruction discovery](https://learn.chatgpt.com/docs/agent-configuration/agents-md).

```text
Use the writing-style skill at ~/.agents/skills/writing-style/SKILL.md for all generated or edited prose, including replies and progress updates. Apply it silently. Explicit requests for another voice, exact text, or a required format take precedence. Preserve code, structured data, and quotations exactly when required.
```

Start a new session and ask which writing instructions are active. Check that the skill is found and the global instruction is loaded. This is a persistent default, not a guarantee that every output will perfectly match the voice. For another agent, install `SKILL.md` through its supported skill mechanism and add the equivalent default to its persistent instructions.

## Privacy

The package contains abstract style guidance, without source addresses, article titles, excerpts, or personal history. The examples are invented and follow the privacy rules at the top of `EXAMPLES.md`. Applying it requires no browsing, account access, or retrieval of past writing. Facts needed for a new task are separate from style-learning material.

This protects the contents of the package; it does not anonymize its owner, erase conversation history, or control provider logs. Before publishing, check repository history and hosting metadata separately.

## Maintenance

Only `SKILL.md` needs to be loaded during use. `EXAMPLES.md` shows the guidance applied to invented before-and-after cases. It is optional calibration material, not a source corpus or an automated test suite. `STYLE_PROFILE.md` records the basis and limits of the guidance.
