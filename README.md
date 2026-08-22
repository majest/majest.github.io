# majest.github.io

The showcase site for the projects Alan and Adam build with Claude.
Live at **https://majest.github.io/**

## How it works

There is no build step here. `index.html` is plain HTML, CSS and JavaScript,
served straight off the `master` branch. `.nojekyll` tells GitHub Pages not to
run Jekyll over it.

The project lists are **not** stored in this repo. Each child's repo publishes
its own GitHub Pages site to this same domain:

| Repo | Publishes to |
| --- | --- |
| [`majest/claude-alan`](https://github.com/majest/claude-alan) | `majest.github.io/claude-alan/` |
| [`majest/claude-adam`](https://github.com/majest/claude-adam) | `majest.github.io/claude-adam/` |

Each of those deploys a `projects.json` alongside the projects themselves. Because
they land on the same origin as this page, `index.html` simply fetches
`claude-alan/projects.json` and `claude-adam/projects.json` and draws a card for
every entry.

That means **no credentials anywhere**. Each repo deploys itself with its own
`GITHUB_TOKEN`; nothing needs write access to anything it doesn't own. When a
child adds a project, their repo republishes and this page shows it on the next load.

## Adding a third child

Add an entry to the `MAKERS` array near the bottom of `index.html`, create the repo
with the same layout, and that's it.

## The old blog

This repo held a Jekyll-Now blog from 2014–15. It was replaced by this site in
August 2026. Nothing was lost — it is preserved in git history and tagged
[`blog-archive-2015`](https://github.com/majest/majest.github.io/tree/blog-archive-2015).

To read it: `git checkout blog-archive-2015`
