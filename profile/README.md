# League Toolkit

> The modding toolkit for League of Legends.

League Toolkit is a community-driven ecosystem of libraries, tools, and applications for creating, editing, and distributing League of Legends mods. We maintain the parsers for Riot's file formats, the CLIs that build mods, and the managers that ship them to players.

- **Wiki & docs:** [wiki.leaguetoolkit.dev](https://wiki.leaguetoolkit.dev/)
- **.bin class reference:** [lol-meta-wiki](https://github.com/LeagueToolkit/lol-meta-wiki)
- **Curated list of League tooling:** [awesome-league](https://github.com/LeagueToolkit/awesome-league)

## Mod managers

End-user applications for installing and running custom skins.

| Project                                                             | Description                                       |
| ------------------------------------------------------------------- | ------------------------------------------------- |
| [**ltk-manager**](https://github.com/LeagueToolkit/ltk-manager)     | Next-generation mod manager (Tauri, React, Rust). |
| [**cslol-manager**](https://github.com/LeagueToolkit/cslol-manager) | The original custom-skin mod manager (C++, Qt).   |

## Core libraries

Reusable libraries for parsing and editing League of Legends asset formats.

| Project                                                               | Language | Description                                                       |
| --------------------------------------------------------------------- | -------- | ----------------------------------------------------------------- |
| [**league-toolkit**](https://github.com/LeagueToolkit/league-toolkit) | Rust     | Modern Rust workspace for League asset formats.                   |
| [**LeagueToolkit**](https://github.com/LeagueToolkit/LeagueToolkit)   | C#       | Long-standing .NET library for parsing and editing League assets. |

## CLIs & utilities

Focused command-line tools for specific formats and workflows.

| Project                                                             | Description                                            |
| ------------------------------------------------------------------- | ------------------------------------------------------ |
| [**league-mod**](https://github.com/LeagueToolkit/league-mod)       | Create, manage, and distribute League of Legends mods. |
| [**wadtools**](https://github.com/LeagueToolkit/wadtools)           | High-performance tooling for `.wad` files.             |
| [**ltk-tex-utils**](https://github.com/LeagueToolkit/ltk-tex-utils) | CLI utilities for working with `.tex` textures.        |
| [**ritobin-tools**](https://github.com/LeagueToolkit/ritobin-tools) | Tooling for Ritobin (`.py`) files.                     |

## Reference data

| Project                                                                   | Description                                           |
| ------------------------------------------------------------------------- | ----------------------------------------------------- |
| [**lol-meta-wiki**](https://github.com/LeagueToolkit/lol-meta-wiki)       | Documentation for `.bin` meta classes and properties. |
| [**lol-meta-classes**](https://github.com/LeagueToolkit/lol-meta-classes) | Per-patch meta class dumps.                           |
| [**LeagueHashes**](https://github.com/LeagueToolkit/LeagueHashes)         | Community-maintained hash lists.                      |

## Contributing

Most of our projects welcome contributions — issues, PRs, and discussion are all fair game. Start with the repo's `README` and open issues. For broader questions about asset formats or modding workflows, the [wiki](https://wiki.leaguetoolkit.dev/) is the best first stop.

League Toolkit is an independent community project. It is not affiliated with or endorsed by Riot Games.
