# Clean Language

**Prefix:** CLN

**Audience:** The people who write the specs of the Clean Language project; whoever builds one of the meta modules of this meta app

**Scope:** What the meta app is, its meta modules, and where each one is installed. Each meta module specifies its own meta use cases and hooks. How the five layers of a project work is in [layers.md](https://github.com/jpchauny/indra-software-factory/blob/main/apps/indra-software-factory/modules/development-methodology/specs/layers.md) of the meta app Indra Software Factory

The meta app of the tooling repository of the project Clean Language, `jpchauny/clean-language-tooling` ([LAY-14](https://github.com/jpchauny/indra-software-factory/blob/main/apps/indra-software-factory/modules/development-methodology/specs/layers.md#the-tooling-repository)), at its root. This repository is a meta repository, developed with the meta methodology of [development.md](https://github.com/jpchauny/indra-software-factory/blob/main/specs/development.md), which it cites by that URL and never copies ([DEV-11](https://github.com/jpchauny/indra-software-factory/blob/main/specs/development.md#method)).

Clean Language is a programming language, specified in a project of five
layers of Indra Software Factory. This meta app holds the plugins that are
specific to that project, and that no other project uses: what they check or
generate is Clean itself. A plugin that serves every project belongs to Indra
Software Factory, not to this meta app.

## Terms

| Term | Meaning |
|---|---|
| Meta app | Clean Language: its meta modules, each one a plugin installed on its own. The meta app itself is no plugin. |
| Meta module | A part of the meta app with one responsibility, its meta use cases, its hooks or both, built as one plugin of the same name ([DEV-7](https://github.com/jpchauny/indra-software-factory/blob/main/specs/development.md#levels)). |
| Meta use case | One thing the user invokes, as `/<module>:<use case>`. |
| The project | The project Clean Language: the repositories that its `project.json` lists, with the layer of each ([LAY-1](https://github.com/jpchauny/indra-software-factory/blob/main/apps/indra-software-factory/modules/development-methodology/specs/layers.md#rules)). |

## Meta modules

| Meta module | Responsibility | Specs |
|---|---|---|
| `clean-examples` | Layers 0 and 1: the rules of how a Clean example is written, the audit of the examples of a layer, and the hook that refuses a malformed example as it is written | [module.md](../modules/clean-examples/specs/module.md) |
| `clean-derived-norms` | Layer 2: the derived norms of Clean, each with its own generator, such as the grammar and the semantics | [module.md](../modules/clean-derived-norms/specs/module.md) |

## Rules

How a meta module is built, one plugin that depends on no other, is [DEV-7](https://github.com/jpchauny/indra-software-factory/blob/main/specs/development.md#levels).

- **CLN-1.** Where each meta module is installed (complete list): each one is a plugin of the marketplace `clean-language-tooling`, the file `.claude-plugin/marketplace.json` of this repository, and is installed from it in the `.claude/settings.json` of these repositories of the project, and of no other repository, as [LAY-14](https://github.com/jpchauny/indra-software-factory/blob/main/apps/indra-software-factory/modules/development-methodology/specs/layers.md#the-tooling-repository) says: the marketplace in `extraKnownMarketplaces`, as `"clean-language-tooling": {"source": {"source": "github", "repo": "jpchauny/clean-language-tooling"}}`, and the plugin in `enabledPlugins`, as `"<module>@clean-language-tooling": true`:

  | Meta module | Repositories |
  |---|---|
  | `clean-examples` | the repository of layer 0 and the repository of layer 1 |
  | `clean-derived-norms` | the repository of layer 2 |

- **CLN-2.** Every meta module obeys the rules of the five layers, the clauses LAY-n of [layers.md](https://github.com/jpchauny/indra-software-factory/blob/main/apps/indra-software-factory/modules/development-methodology/specs/layers.md#rules).