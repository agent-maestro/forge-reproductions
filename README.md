# Forge reproduction packages

Each release of this repository is one claim made by [Monogate Forge](https://monogateforge.com), packaged so that an
engineer outside the project can check it without Forge: the claim's terms, its evidence, and the scripts that check
it. The package is the release's asset, a `.tar.gz` that GitHub keeps immutable and lists with its sha256; the
package's own `README.md` says what it claims, what it checks, and what you are trusting.

Every package is checkable at up to three tiers, as on [the zoo](https://zoo.monogateforge.com):

- **LOCAL**: one command, the standard library and one Python package, seconds;
- **TOOLCHAIN**: re-derive what the evidence rests on with the toolchain it names (a simulator, a prover);
- **REPLAY**: re-run it on the same hardware.

## Checking a release's asset

    sha256sum forge-*.tar.gz        # compare with the digest the release lists
    tar xzf forge-*.tar.gz && cd forge-*/ && python3 check.py

## Packages

| release | claim | status |
|---|---|---|
| T5 (`camera_fov_t5`, 2026-11-06) | `2*atan(u)` on an Arty A7-100T: every one of 26,211 inputs within a certified error bound, checked on the board | to be released |

Forge's own repository is private; nothing here needs it. Each package carries its own licence (`LICENSE` inside the
tar); this repository's own files are under `LICENSE` here.
