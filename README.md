# Perun for Obsidian

Run live circuit simulations in your notes, and edit `.circuit` files in the full Perun circuit
editor. Perun is a rebuild of Paul Falstad's [CircuitJS1](https://github.com/pfalstad/circuitjs1):
circuits from CircuitJS1 open and run the same way.

- **Circuit blocks.** A code block whose language is `circuit` shows the circuit running, with its
  scopes, in reading view and live preview. Paste any CircuitJS1 or Perun circuit, text or XML:

  ````md
  ```circuit
  $ 1 0.000005 10.2 50 5 50 5e-11
  r 96 112 240 112 0 220
  w 96 112 96 240 0
  w 240 112 240 240 0
  v 96 240 240 240 0 0 40 5 0 0 0.5
  ```
  ````

- **Embedded circuit files.** `![[name.circuit]]` shows that file running, and follows it when the
  file changes.
- **Under each circuit:** Pause and Run, Reset, the circuit's own sliders, and Open in Perun.
  Switches, push buttons and logic inputs can be clicked right in the note. Printing and Export to
  PDF show a sharp still picture.
- **Circuit files.** A `.circuit` file opens the whole Perun editor in a tab: parts palette,
  scopes, analysis and themes. Every edit is saved to the file, so it syncs and versions like any
  other note. Exported images and CSV files are saved into the vault next to it.
- **Themes.** Circuits follow Obsidian's light and dark mode, or any of Perun's themes.

It works on desktop and on Obsidian for iPhone, iPad and Android. It needs no account and sends
nothing anywhere.

**Network use.** The editor's example circuits and its menus in other languages (about 1.7 MB) are
kept out of the plugin itself. The first time a circuit file opens, the plugin downloads them once,
as `perun-files.json`, from the release of its own version on
[GitHub](https://github.com/noiseweaver/Perun/releases), and keeps them in its folder. Until then,
or offline, the editor has no examples and its menus are in English. Nothing else goes over the
network.

## Install

In Obsidian, Settings > Community plugins > Browse, search for Perun. Until it is listed there, use
the [BRAT](https://github.com/TfTHacker/obsidian42-brat) plugin: Add beta plugin,
`noiseweaver/perun-obsidian`.

## About this repository

This is the release mirror of [noiseweaver/Perun](https://github.com/noiseweaver/Perun), where
Perun is developed. Each plugin release there is copied here: the source at that release (the
plugin is `packages/obsidian`, built from the other packages), `manifest.json`, and a release with
the same files. Please open issues and pull requests in
[noiseweaver/Perun](https://github.com/noiseweaver/Perun).

To build the plugin from this source: `git submodule update --init --depth 1` (the upstream
CircuitJS1 examples and translations), `pnpm install`, then `pnpm --filter @perun/obsidian build`
(the files land in `packages/obsidian/dist`).

## License

GPL-2.0-or-later (see [LICENSE](LICENSE)). Based on CircuitJS1 by Paul Falstad and Iain Sharp.
Perun by Gadiel Zintu.
