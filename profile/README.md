<div align="center">
  <a href="https://github.com/LeagueToolkit">
    <img src="https://avatars.githubusercontent.com/u/28510182?s=200&v=4" alt="LeagueToolkit logo" width="96" height="96">
  </a>
  <h1>League Toolkit</h1>
</div>

League of Legends keeps its art and data in formats Riot does not document: `.wad` archives
holding `.bin` data, `.tex` textures, `.skn` models, `.anm` animations. League Toolkit documents
those formats and builds the software that reads and writes them. The libraries under other
people's tools, the tools that turn a folder of files into a mod, and the managers that install
one are all here.

<div align="center">

**[Play mods](#play-mods)** · **[Make mods](#make-mods)** · **[Build tools](#build-tools)** · **[Reference data](#reference-data)**

</div>

## Play mods

[**ltk-manager**](https://github.com/LeagueToolkit/ltk-manager) is the current mod manager. It
holds a library of mods, enables and disables them, and patches the game.

[**cslol-manager**](https://github.com/LeagueToolkit/cslol-manager) is the long-standing one. Old
guides and skin downloads assume it.

## Make mods

A mod puts your own files where the game expects Riot's. The
[**wiki**](https://wiki.leaguetoolkit.dev/) covers the project layout and the path a mod takes
into the game.

[**league-mod**](https://github.com/LeagueToolkit/league-mod) defines `.modpkg`, the format a
finished mod ships in. It packs a project directory into one and builds the WAD overlay the game
loads. ltk-manager runs on it.

[**wadtools**](https://github.com/LeagueToolkit/wadtools) extracts, lists and compares `.wad`
archives, and adds itself to the Windows right-click menu.
[**ltk-tex-utils**](https://github.com/LeagueToolkit/ltk-tex-utils) converts and inspects `.tex`
textures. [**ritobin-tools**](https://github.com/LeagueToolkit/ritobin-tools) works on Ritobin
files, the readable text form of `.bin` data.

## Build tools

[**league-toolkit**](https://github.com/LeagueToolkit/league-toolkit) is a set of Rust crates, one
per format family: WAD archives, property bins, textures, meshes, animations, map geometry, string
tables. Depend on the umbrella crate, or on a single crate.

[**LeagueToolkit**](https://github.com/LeagueToolkit/LeagueToolkit) is the C# library for the same
formats.

A WAD stores paths as hashes. A name comes back through a hash table.
[**Mimir**](https://github.com/LeagueToolkit/Mimir) delivers those tables as compact
memory-mapped files, shared between tools through one cache.

## Reference data

The [**wiki**](https://github.com/LeagueToolkit/wiki) holds our guides and format documentation,
published at [wiki.leaguetoolkit.dev](https://wiki.leaguetoolkit.dev/).

[**lol-meta-wiki**](https://github.com/LeagueToolkit/lol-meta-wiki) documents every `.bin` meta
class and property, with a JSON API and per-patch changelogs. It renders
[**lol-meta-classes**](https://github.com/LeagueToolkit/lol-meta-classes), a dump of those classes
taken every patch.

[**ritobin-lang**](https://github.com/LeagueToolkit/ritobin-lang) specifies the Ritobin language.
[**LeagueHashes**](https://github.com/LeagueToolkit/LeagueHashes) collects the community's hash
lists. [**awesome-league**](https://github.com/LeagueToolkit/awesome-league) is a curated list of
League tooling, ours and everyone else's.

## Older projects

[**Fantome**](https://github.com/LeagueToolkit/Fantome) is archived. league-mod reads and writes
the `.fantome` format it introduced, and old mods keep working.
[**LeagueFileTranslator**](https://github.com/LeagueToolkit/LeagueFileTranslator) is a Maya 2019
plugin for League models and animations.
[**LeagueDownloader**](https://github.com/LeagueToolkit/LeagueDownloader) downloads any released
version of the game.

## Contributing

Issues, pull requests and questions are welcome on every repository here. Anything beyond a small
fix starts as an issue. The
[contributing guide](https://github.com/LeagueToolkit/.github/blob/main/CONTRIBUTING.md) covers
setup, style and review across the org.
[repo-template](https://github.com/LeagueToolkit/repo-template) is the starting point for a new
repository.

Documenting a format nobody has written up yet counts as much as code. The wiki is where it goes.

League Toolkit is an independent community project. It is not affiliated with or endorsed by Riot
Games.
