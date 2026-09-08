<div align="center">
  <a href="https://github.com/LeagueToolkit">
    <img src="https://avatars.githubusercontent.com/u/28510182?s=200&v=4" alt="LeagueToolkit logo" width="96" height="96">
  </a>
  <h1>League Toolkit</h1>
</div>

League of Legends keeps its art and data in formats Riot never documented - `.wad` archives full
of `.bin` data, `.tex` textures, `.skn` models, `.anm` animations. We work out how those formats
are put together and build the software that reads and writes them: the libraries other people's
tools are built on, the tools that turn a folder of files into a mod, and the managers that put
that mod into the game.

<div align="center">

**[Play mods](#play-mods)** · **[Make mods](#make-mods)** · **[Build tools](#build-tools)** · **[Reference data](#reference-data)**

</div>

## Play mods

If you are here to put custom skins in your game, you want a mod manager. Install
[**ltk-manager**](https://github.com/LeagueToolkit/ltk-manager), our current one - it keeps your
mods in a library, turns them on and off, and patches the game so they show up in a match.

[**cslol-manager**](https://github.com/LeagueToolkit/cslol-manager) is the manager most people
have been using for years, and it still works. Old guides and skin downloads assume it, so it is
worth knowing what it is even if you start with ltk-manager.

## Make mods

Making a mod means putting your own files where the game expects Riot's. The
[**wiki**](https://wiki.leaguetoolkit.dev/) is the place to start: it walks through how a mod
project is laid out, what goes in it, and how it reaches the game.

[**league-mod**](https://github.com/LeagueToolkit/league-mod) is the machinery underneath that.
It defines `.modpkg`, the format a finished mod ships in, packs a project directory into one, and
builds the WAD overlay the game actually loads. ltk-manager uses it for everything it does to a
mod, so what you build locally and what a player installs go through the same code.

Around it sit smaller tools for the individual formats.
[**wadtools**](https://github.com/LeagueToolkit/wadtools) opens up `.wad` archives - extract them,
list what is inside, compare two of them - and adds itself to the Windows right-click menu.
[**ltk-tex-utils**](https://github.com/LeagueToolkit/ltk-tex-utils) converts and inspects `.tex`
textures. [**ritobin-tools**](https://github.com/LeagueToolkit/ritobin-tools) handles Ritobin
files, the readable text form of `.bin` data that you can edit by hand.

## Build tools

If you are writing your own tool, start with
[**league-toolkit**](https://github.com/LeagueToolkit/league-toolkit). It is a set of Rust crates,
one per format family: WAD archives, property bins, textures, meshes, animations, map geometry and
string tables. Take the whole thing or depend on the one crate you need.

[**LeagueToolkit**](https://github.com/LeagueToolkit/LeagueToolkit) is the C# library that came
first and still covers most of the same formats, for anyone working in .NET.

Names are the recurring problem in all of this: a WAD stores paths as hashes, so a file's name has
to be looked up in a hash table. [**Mimir**](https://github.com/LeagueToolkit/Mimir) turns those
tables into a compact memory-mapped file with a shared cache, so several tools can use one copy
instead of each parsing hundreds of megabytes of text.

## Reference data

The [**wiki**](https://github.com/LeagueToolkit/wiki) holds our guides and format documentation,
published at [wiki.leaguetoolkit.dev](https://wiki.leaguetoolkit.dev/).

For `.bin` data specifically, [**lol-meta-wiki**](https://github.com/LeagueToolkit/lol-meta-wiki)
documents every meta class and property, with a JSON API and a changelog of what each patch
changed. It is generated from [**lol-meta-classes**](https://github.com/LeagueToolkit/lol-meta-classes),
which dumps those classes fresh every patch.
[**ritobin-lang**](https://github.com/LeagueToolkit/ritobin-lang) specifies the Ritobin language
itself, and [**LeagueHashes**](https://github.com/LeagueToolkit/LeagueHashes) collects the
community's hash lists.

Looking for something we don't make?
[**awesome-league**](https://github.com/LeagueToolkit/awesome-league) is a curated list of League
tooling, ours and everyone else's.

## Older projects

Some of our repositories are here for the people who arrive from an old guide or forum post.
[**Fantome**](https://github.com/LeagueToolkit/Fantome) is archived, though the `.fantome` format
it introduced is still read and written by league-mod, so old mods keep working.
[**LeagueFileTranslator**](https://github.com/LeagueToolkit/LeagueFileTranslator) is a Maya 2019
plugin for League models and animations, and
[**LeagueDownloader**](https://github.com/LeagueToolkit/LeagueDownloader) downloads any released
version of the game.

## Contributing

Issues, pull requests and questions are welcome on any of these. Read the repository's README and
its open issues first, and for anything beyond a small fix, open an issue before you write code so
we can agree on the shape of it. The
[contributing guide](https://github.com/LeagueToolkit/.github/blob/main/CONTRIBUTING.md) covers
setup, style and review across the org, and
[repo-template](https://github.com/LeagueToolkit/repo-template) is what a new repository starts
from.

You do not have to write code to help. Working out a format nobody has documented yet, and writing
it up on the wiki, is the most useful thing anyone does here.

League Toolkit is an independent community project. It is not affiliated with or endorsed by Riot
Games.
