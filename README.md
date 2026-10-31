# clean-language-tooling

The tooling repository: no layer. The project's own plugins, and the Claude Code marketplace `clean-language-tooling` that the repositories of the layers install them from ([LAY-14](https://github.com/jpchauny/indra-software-factory/blob/main/apps/indra-software-factory/modules/development-methodology/specs/layers.md#the-tooling-repository)).

Part of `clean-language`, worked in five layers, with a tooling repository: [clean-language-foundation-drafts](https://github.com/Ivan-Pasco/clean-language-foundation-drafts), [clean-language-foundation](https://github.com/Ivan-Pasco/clean-language-foundation), [clean-language-norms](https://github.com/Ivan-Pasco/clean-language-norms), [clean-language-acceptance](https://github.com/Ivan-Pasco/clean-language-acceptance), [clean-language-compiler](https://github.com/Ivan-Pasco/clean-language-compiler), [clean-host-core](https://github.com/Ivan-Pasco/clean-host-core), [clean-server](https://github.com/Ivan-Pasco/clean-server), [clean-language-tooling](https://github.com/jpchauny/clean-language-tooling). The process: [layers](https://github.com/jpchauny/indra-software-factory/blob/main/apps/indra-software-factory/modules/development-methodology/specs/layers.md).

It holds the meta app Clean Language, at its root ([specs/app.md](specs/app.md)): its meta modules, each a plugin of this marketplace, in `modules/<module>/`.

| Plugin | Installed in |
|---|---|
| `clean-examples` | the repositories of layers 0 and 1 |
| `clean-derived-norms` | the repository of layer 2 |

## Tests

From the root of this repository.

`clean-derived-norms` (the tests that build Lean are skipped when `lake` is absent):

```sh
uv run --with pytest --with "lark[interegular]" python3 -I -B -m pytest -q -p no:cacheprovider modules/clean-derived-norms/tests
```

`clean-examples`:

```sh
python3 -m unittest discover -s modules/clean-examples/tests
```
