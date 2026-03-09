# mylan.io

Personal developer portfolio and blog built with [Hugo](https://gohugo.io/) and the [HugoBlox](https://hugoblox.com/) Developer Portfolio theme.

## Development

This project uses a Nix flake for development dependencies. With [direnv](https://direnv.net/) configured:

```bash
# Install Node dependencies
pnpm install

# Download Hugo modules
hugo mod tidy

# Start the dev server
pnpm run dev
```

The site will be available at `http://localhost:1313`.

## Build

```bash
pnpm run build
```

This runs `hugo --minify` followed by `pagefind` to generate the search index.

## Deployment

The site is automatically deployed to [GitHub Pages](https://pages.github.com/) on push to `main` via GitHub Actions. It is served at [https://mylan.io](https://mylan.io).
