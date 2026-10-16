# prism-sources

The source of every program the [PRISM](https://github.com/jfrelat-lab/prism) site runs, as it was
built. PRISM compiles the unmodified source of DOS-era and early-Linux games and programs to
JavaScript; the site ships those builds, and a build is object code, so its source travels with it.

Each **release** belongs to one export of the site (tag `site-<date>`). Its assets are:

- one `<tree>.tar.gz` per source tree a shipped build was made from, exactly as its publisher released
  it -- PRISM never edits a program's source;
- `build-scripts.tar.gz`: what controls those builds -- one `targets/<program>.json` per program (its
  units, defines and options) and the tools that wrote the generated trees (the `*-generated`
  archives: what each program's own `configure` wrote);
- `README.txt`, with where each tree was fetched from and the commit of PRISM that built the export;
- `SHA256SUMS`.

The archives are published by `tools/publish-sources.mjs` in PRISM's repository and never replaced:
the site's pages link to them, so a release's files stay what that export was built from.

Each program keeps its own licence, inside its archive. Nothing here is game data.
