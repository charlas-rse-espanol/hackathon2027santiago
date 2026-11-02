# Hackathon RSE Santiago 2027

Website for the Hackathon RSE Santiago 2027, a hackathon for people who develop research software, held in Santiago de Chile. It is organised by [Charlas RSE en español](https://charlas-rse-espanol.github.io/), [RSE Chile](https://rse-chile.github.io/) and [RSE Argentina](https://rse-argentina.github.io/).

The site is in Spanish. It is built with [Hugo](https://gohugo.io/) and [Tailwind CSS v4](https://tailwindcss.com/), on top of the [Hugoplate](https://github.com/zeon-studio/hugoplate) theme.

## Editing the home page

The home page content is in Markdown front matter under [`content/spanish/`](content/spanish/). Each section of the page reads from one file:

| Home page section | File to edit |
| --- | --- |
| Banner (title, intro text, image, "Más información" button) | [`content/spanish/_index.md`](content/spanish/_index.md), under `banner:` |
| Feature blocks ("¿Qué es el Hackathon RSE?", "¿Quién puede participar?") | [`content/spanish/_index.md`](content/spanish/_index.md), under `features:` (each `- title:` is one block; add or remove blocks as needed) |
| Organisers ("Organizan") logos | [`content/spanish/sections/organizan.md`](content/spanish/sections/organizan.md) |
| Supporters ("Apoyos") logos | [`content/spanish/sections/apoyos.md`](content/spanish/sections/apoyos.md) |
| Host ("Anfitrión") logo | [`content/spanish/sections/anfitrion.md`](content/spanish/sections/anfitrion.md) |

Notes:

- Images referenced as `/images/...` (for example `banner.png` or the organisation logos) live in [`assets/images/`](assets/images/).
- The layout and order of the sections are set in [`layouts/home.html`](layouts/home.html), and the logo sections are drawn by [`layouts/_partials/organizations.html`](layouts/_partials/organizations.html). You only need to touch these to change the structure or order, not the text.
- The header menu, footer and site title come from [`config/_default/`](config/_default/) (`menus.es.toml`, `params.toml`) and [`hugo.toml`](hugo.toml), not from the home page files.

## Other content

- The "Sobre el hackathon" page (dates, venue, programme, how to apply) is in [`content/spanish/sobre-el-hackathon/_index.md`](content/spanish/sobre-el-hackathon/_index.md).
- Colours and fonts are set in [`data/theme.json`](data/theme.json).
- Logo, favicon, SEO metadata and other site parameters are in [`config/_default/params.toml`](config/_default/params.toml).

## Running the site locally

### Prerequisites

- [Hugo Extended](https://gohugo.io/installation/), **exactly** the version set as `HUGO_VERSION` in [`netlify.toml`](netlify.toml) (currently `0.158.0`)
- [Node v22+](https://nodejs.org/en/download/)
- [Go v1.24+](https://go.dev/doc/install) (used by Hugo Modules)

This project uses **npm** as its package manager.

Homebrew and most package managers only install the latest Hugo. To get the exact version this project needs, use [mise](https://mise.jdx.dev/), which reads the version pinned in [`mise.toml`](mise.toml):

```bash
brew install mise                # or see https://mise.jdx.dev/getting-started.html
eval "$(mise activate zsh)"      # add this line to ~/.zshrc to make it permanent
mise install                     # run from the repository root
hugo version                     # should print v0.158.0+extended
```

### Commands

> [!IMPORTANT]
> Before running any of the commands below, activate mise in your shell so that `hugo` resolves to the pinned 0.158.0 version:
>
> ```bash
> eval "$(mise activate zsh)"
> hugo version                     # should print v0.158.0+extended
> ```
>
> Without this, your shell may pick up another Hugo installation (for example a newer version from Homebrew). The build then fails, for example with a Tailwind CSS `security.exec.allow` error.

Always use these npm scripts rather than running `hugo` directly, because they also regenerate the theme CSS.

| Command | Use |
| --- | --- |
| `npm install` | Install dependencies (first run, or after pulling changes) |
| `npm run dev` | Development server with live reload, at <http://localhost:1313> |
| `npm run build` | Production build to `public/` |
| `npm run preview` | Production-flavoured local server |

After changing content or layouts, restart the development server if the changes don't show up:

```bash
npx kill-port 1313 -y && npm run dev
```

## Repository structure

The site lives at the repository root and the Hugoplate theme is vendored in [`themes/hugoplate/`](themes/hugoplate/). Files in the root [`layouts/`](layouts/) override the theme's templates of the same name, so make template changes there and leave `themes/hugoplate/` untouched.

This repository has already been converted to this structure with `npm run project-setup`. Running it again is harmless.

## Deployment

Pushing to `main` builds the site and deploys it to GitHub Pages, using the workflow in [`.github/workflows/main.yml`](.github/workflows/main.yml).

## Credits and licence

The site is based on [Hugoplate](https://github.com/zeon-studio/hugoplate) by [Zeon Studio](https://zeon.studio/), released under the [MIT licence](LICENSE).
