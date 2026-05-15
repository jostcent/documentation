# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Build Commands

Install dependencies (Python 3.12 required):
```bash
pip install -r requirements.txt
```

Build all three HTML manuals:
```bash
make html
```

Build a single manual:
```bash
cd user_manual && make html
cd admin_manual && make html
cd developer_manual && make html
```

Live-reload preview (any manual — opens http://127.0.0.1:8000):
```bash
pip install sphinx-autobuild
cd user_manual && make SPHINXBUILD=sphinx-autobuild html
```

Build PDFs (Docker recommended — see README.rst for the full Docker command):
```bash
cd user_manual && make latexpdf
```

Build the developer manual (requires fetching the OpenAPI spec first):
```bash
make openapi-spec          # fetches server sources and Stoplight assets
cd developer_manual && make html
```

Check spelling:
```bash
codespell                  # config in .codespellrc; ignored words in .codespellignore
```

Clean all build output:
```bash
make clean
```

## Architecture

This is the Nextcloud documentation repository — a **Sphinx / reStructuredText** project built around three independent manuals:

- `user_manual/` — end-user guide
- `admin_manual/` — administrator guide
- `developer_manual/` — developer guide

Each manual is self-contained with its own `conf.py`, `Makefile`, and `_build/` output directory. The root `conf.py` defines shared Sphinx configuration (theme, extensions, version constants) that each manual's `conf.py` imports via a `sys.path` insert.

### Sphinx extensions in use

`sphinx_rtd_theme`, `sphinx_rtd_dark_mode`, `sphinx_copybutton`, `sphinxcontrib.mermaid`, `notfound.extension`, `sphinx-reredirects`, `sphinxcontrib-phpdomain`.

### Version and branch strategy

- `master` → "latest" docs (`https://docs.nextcloud.com/server/latest/`)
- `stable<N>` → versioned releases (`stable32` is the current stable, symlinked to `/server/stable/`)
- The `version_stable` constant in root `conf.py` must be updated and matched by a symlink change on the live server when a new stable is cut
- Changes affecting multiple versions require backporting to each relevant `stable*` branch

### Developer manual OpenAPI dependency

`developer_manual/` embeds an interactive API reference powered by Stoplight Elements. The `make openapi-spec` target (root Makefile) runs `build/get-server-sources.sh` to clone the Nextcloud server at the matching branch and copy `openapi.json`, then downloads the Stoplight JS/CSS assets. In CI this step is omitted; the committed static file is used instead.

### Shared assets

`_shared_assets/` holds the Nextcloud logo and shared CSS referenced by all manuals via a relative `../_shared_assets/` path in each manual's `conf.py`.

### `_ext/` directory

Contains custom Sphinx extensions loaded via the `sys.path` insert in root `conf.py`.

## Content Conventions

### RST formatting rules

- Wrap lines at **80 characters**
- Use exactly **three heading levels**; restructure rather than add a fourth:
  ```
  ==============
  Page title (h1)
  ==============

  Section (h2)
  -----------

  Subsection (h3)
  ^^^^^^^^^^^
  ```
- GUI element names in **bold**: `**Username** field`, `**Create** button`
- Commands and inline code in double-backticks: ` ``sudo occ maintenance:install`` `
- Example URLs written as inline code, not live links: ` ``https://example.com`` `
- `.. figure::` directives must have `:alt:` tags and italicized captions with figure numbers: `*Figure 1: …*`

### File and image naming

- Page filenames: lowercase with underscores (`file_name_config.rst`)
- Image filenames: lowercase with hyphens (`image-name.png`), PNG only
- Images go in a chapter-local `images/` subdirectory, not a root-level images directory

### Spelling and capitalization

Enforced by `codespell` (CI). Canonical spellings:
- "Nextcloud App Store" (capital A and S)
- "synchronize" (not "sync" in prose)
- "Web page", "Web site" (capital W)

Words exempted from spell-checking are listed in `.codespellignore`.

### Auto-generated file — never edit directly

`admin_manual/configuration_server/config_sample_php_parameters.rst` is generated from `nextcloud/server`'s `config/config.sample.php`. All changes must be made upstream in the server repository.

### Page stability — no renames or moves without redirects

External sites and search engines link to specific URLs. If a page must be moved or renamed, a redirect must be added via the `sphinx-reredirects` extension. Treat page paths like a public API.

## Commit Requirements

All commits must include a DCO sign-off:

```
Signed-off-by: Your Name <your.email@example.com>
```

Use `git commit -s` to add this automatically. The email must match your GitHub profile email (privacy users: `username@users.noreply.github.com`).
