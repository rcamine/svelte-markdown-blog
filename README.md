# Markdown Blog

Minimalistic blog site template using Markdown for [my blog site](https://rcamine.com), built with [Svelte](https://svelte.dev), [SvelteKit](https://kit.svelte.dev), [MDsveX](https://mdsvex.com), [TailwindCSS](https://tailwindcss.com/) and [DaisyUI](https://daisyui.com/).

## Getting started

First, clone the repository and navigate to the project directory:

```bash
git clone https://github.com/rcamine/svelte-markdown-blog.git
cd svelte-markdown-blog
```

Next, install dependencies with NPM:

```bash
npm install
```

Finally, run the local development server:

```bash
npm run dev
```

Your posts should be in the `posts` root folder.

```bash
markdown-blog/
├─ posts/
│ └─ your-post/
│   └─ index.md
├─ src/
│ └─ lib/
│ └─ routes/
...rest of the files
```
If your `index.md` file has the metadata `published` set to `true`, it will be automatically published on the home page. 

```yaml
---
date: 2022-01-01
title: My title
published: true
tags:
  - personal
---
```

## Deploying

My recommendation is using [Vercel](https://vercel.com/docs/concepts/git), it's very easy to integrate with Github and it will automatically deploy to your domain after every push on your repository.
