# nene-corpus-site

Product website monorepo for [NeNe Corpus](https://github.com/hideyukiMORI/nene-corpus).

| App | URL | Audience |
|---|---|---|
| `apps/com` | nene-corpus.com | Japanese SMB operators (marketing LP) |
| `apps/dev` | nene-corpus.dev | Developers (API docs, architecture) |

## Stack

- [Astro 6](https://astro.build/) — static site generation
- [Tailwind CSS v4](https://tailwindcss.com/) — styling
- npm workspaces — monorepo
- Deployed to [ヘテムル](https://heteml.jp/) shared hosting via FTP

## Development

```bash
npm install

# nene-corpus.com
npm run dev:com     # http://localhost:4321

# nene-corpus.dev
npm run dev:dev     # http://localhost:4322
```

## Build

```bash
npm run build         # build both
npm run build:com     # apps/com/dist/
npm run build:dev     # apps/dev/dist/
```

Deploy each `dist/` directory to the corresponding domain on ヘテムル via FTP.

> **Note:** `.dev` requires HTTPS (HSTS preloaded). Enable Let's Encrypt SSL on ヘテムル before going live.

## Repository structure

```
nene-corpus-site/
  apps/
    com/      # nene-corpus.com — Japanese LP
    dev/      # nene-corpus.dev — Developer docs
  packages/
    ui/       # Shared CSS tokens & utilities
  .github/
    workflows/
      build.yml   # CI build check
```
