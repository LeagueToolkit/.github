<div align="center">
  <a href="https://github.com/LeagueToolkit">
    <img src="https://avatars.githubusercontent.com/u/28510182?s=200&v=4" alt="LeagueToolkit logo" width="96" height="96">
  </a>
  <h1>League Toolkit</h1>
</div>

Libraries, tools, and applications for creating, editing, and distributing League of Legends mods.
We maintain the parsers for Riot's file formats - `.wad`, `.bin`, `.tex`, `.skn`, `.anm`,
`.mapgeo` - the tools that build mods out of them, and the managers that install those mods for
players.

<div align="center">

**[Play mods](#play-mods)** · **[Make mods](#make-mods)** · **[Build tools](#build-tools)** · **[Reference data](#specs-and-reference-data)**

</div>

## Play mods

Install and run custom skins.

| Project | Description |
| --- | --- |
| [**ltk-manager**](https://github.com/LeagueToolkit/ltk-manager) | The current mod manager. Tauri, React, Rust. |
| [**cslol-manager**](https://github.com/LeagueToolkit/cslol-manager) | The original custom-skin manager. C++, Qt. |

## Make mods

Start at the [wiki](https://wiki.leaguetoolkit.dev/) - it covers the mod project layout, the
`.modpkg` format, and how a mod reaches the game. From there:

| Project | Description |
| --- | --- |
| [**league-mod**](https://github.com/LeagueToolkit/league-mod) | The `.modpkg` format, mod project packing, and the WAD overlay builder. |
| [**wadtools**](https://github.com/LeagueToolkit/wadtools) | Extract, list, and compare `.wad` archives, with Windows Explorer integration. |
| [**ltk-tex-utils**](https://github.com/LeagueToolkit/ltk-tex-utils) | Convert and inspect `.tex` textures. |
| [**ritobin-tools**](https://github.com/LeagueToolkit/ritobin-tools) | Work with Ritobin (`.py`) files, the text form of `.bin`. |

## Build tools

Libraries to write your own tooling against.

| Project | Language | Description |
| --- | --- | --- |
| [**league-toolkit**](https://github.com/LeagueToolkit/league-toolkit) | Rust | Format crates: WAD, property bins, textures, meshes, animations, map geometry, string tables. |
| [**LeagueToolkit**](https://github.com/LeagueToolkit/LeagueToolkit) | C# | The long-standing .NET library for the same formats. |
| [**Mimir**](https://github.com/LeagueToolkit/Mimir) | Rust | Hash-to-path tables as compact memory-mapped files, plus a shared cache. |

## Specs and reference data

| Project | Description |
| --- | --- |
| [**wiki**](https://github.com/LeagueToolkit/wiki) | Source of [wiki.leaguetoolkit.dev](https://wiki.leaguetoolkit.dev/), our guides and format documentation. |
| [**lol-meta-wiki**](https://github.com/LeagueToolkit/lol-meta-wiki) | `.bin` class and property reference, with a JSON API and per-patch changelogs. |
| [**lol-meta-classes**](https://github.com/LeagueToolkit/lol-meta-classes) | Per-patch meta class dumps, the data behind lol-meta-wiki. |
| [**ritobin-lang**](https://github.com/LeagueToolkit/ritobin-lang) | The Ritobin language specification and the standards around it. |
| [**LeagueHashes**](https://github.com/LeagueToolkit/LeagueHashes) | Community-maintained hash lists. |
| [**awesome-league**](https://github.com/LeagueToolkit/awesome-league) | Curated list of League tooling, ours and everyone else's. |

## Older projects

Superseded, but still where people land from old guides and forum posts.

- [**Fantome**](https://github.com/LeagueToolkit/Fantome) - archived. The `.fantome` format it
  introduced is still read and written by league-mod.
- [**LeagueFileTranslator**](https://github.com/LeagueToolkit/LeagueFileTranslator) - Maya 2019
  plugin for League models and animations.
- [**LeagueDownloader**](https://github.com/LeagueToolkit/LeagueDownloader) - downloads any
  released version of the game.

## Contributing

Issues, PRs, and questions are welcome across all of these. Read the repo's README and its open
issues first; anything non-trivial is worth an issue before a PR. The org-wide
[contributing guide](https://github.com/LeagueToolkit/.github/blob/main/CONTRIBUTING.md) covers
setup, style, and review, and [repo-template](https://github.com/LeagueToolkit/repo-template)
holds the conventions a new repo starts from.

Documenting a format nobody has written up yet is the most useful thing you can do here, and the
wiki is where it goes.

League Toolkit is an independent community project. It is not affiliated with or endorsed by Riot
Games.
