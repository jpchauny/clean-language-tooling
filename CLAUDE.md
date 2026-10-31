# CLAUDE.md

## What this repository is

The tooling repository of `clean-language`: no layer. It holds the project's own
code, its plugins, such as the derived-norms generators of layer 2 and the
helpers of layers 0 and 1, with their specs and their tests, and is the Claude
Code marketplace `clean-language-tooling` from which the repositories of the layers
install them ([LAY-14](https://github.com/jpchauny/indra-software-factory/blob/main/apps/indra-software-factory/modules/development-methodology/specs/layers.md#the-tooling-repository)). The
repositories of layers 0 to 3 hold no tool ([LAY-13](https://github.com/jpchauny/indra-software-factory/blob/main/apps/indra-software-factory/modules/development-methodology/specs/layers.md#rules)).

| Layer | Repository |
|---|---|
| 0. Drafts | `Ivan-Pasco/clean-language-foundation-drafts` |
| 1. Specs | `Ivan-Pasco/clean-language-foundation` |
| 2. Norms | `Ivan-Pasco/clean-language-norms` |
| 3. Acceptance | `Ivan-Pasco/clean-language-acceptance` |
| 4. Code | `Ivan-Pasco/clean-language-compiler` |
| 4. Code | `Ivan-Pasco/clean-host-core` |
| 4. Code | `Ivan-Pasco/clean-server` |
| Tooling (no layer) | `jpchauny/clean-language-tooling` (this one) |

The meta app Clean Language is at the root: its meta spec [specs/app.md](specs/app.md), and its meta modules, each one plugin, in `modules/<module>/`. How to run the tests is in [README.md](README.md).

## Working here

- Develop with the meta methodology, by [development.md](https://github.com/jpchauny/indra-software-factory/blob/main/specs/development.md), cited here and never copied: every change starts in a spec, the person approves it, and the implementation follows from it alone. Write each spec by [writing-specs.md](https://github.com/jpchauny/indra-software-factory/blob/main/specs/writing-specs.md).
- Never develop here with the modules of Indra Software Factory: none but `utilities` is enabled, and these specs are no layer 1, have no norm and go through no run.
- Each plugin is listed in `.claude-plugin/marketplace.json`, and has a `version` in its `.claude-plugin/plugin.json`; a derived-norms generator changes its `version` whenever its behaviour changes ([NRM-5 and NRM-7](https://github.com/jpchauny/indra-software-factory/blob/main/apps/indra-software-factory/modules/norms-management/specs/module.md#derive-the-derived-norms)).
- A repository of a layer that uses a plugin of this repository installs it in its `.claude/settings.json`: the marketplace in `extraKnownMarketplaces`, as `"clean-language-tooling": {"source": {"source": "github", "repo": "jpchauny/clean-language-tooling"}}`, and the plugin in `enabledPlugins`, as `"<plugin>@clean-language-tooling": true` ([LAY-14](https://github.com/jpchauny/indra-software-factory/blob/main/apps/indra-software-factory/modules/development-methodology/specs/layers.md#the-tooling-repository)).
- Open this repository alone in its VS Code window: a folder added to the same workspace becomes readable and writable from the session.

## Issues

Pending items and findings go to the issue tree with `/utilities:issue`.
