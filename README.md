# junayeed.dev

Single-page personal site. SvelteKit compiled to static HTML — no runtime.

## Stack

- Svelte 5 / SvelteKit 3 / Vite 8 / adapter-static
- Bun for install + build (CI: oven-sh/setup-bun)
- Deploys to GitHub Pages via GitHub Actions on every push to `main`

## Develop

    bun install
    bun run dev

## Build

    bun run build   # outputs to build/

## Assets

`Images/`, `PDF/`, `Tools/`, `Image.png` are legacy assets kept for reference;
they are not part of the deployed site.
