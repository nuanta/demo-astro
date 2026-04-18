# Nuanta + Astro Demo

This repository is a demonstration of how to automatically publish SEO-optimized articles from **Nuanta** directly to an **Astro** static site using a GitHub Actions `repository_dispatch` webhook.

## What is Nuanta?

[Nuanta](https://nuanta.io) is a data-driven SEO and content marketing platform that:
- **Builds a Knowledge Base:** Crawls your existing website to learn your niche, tone, and context.
- **Analyzes Search Data:** Connects to Google Search Console to track performance, spot keyword cannibalization, and find position declines.
- **Finds Content Gaps:** Automatically generates topic ideas based on what top competitors rank for that you don't.
- **Writes Expert Content:** Uses AI and live competitor research to draft long-form, high-quality articles.

## How the GitHub Actions Integration Works

Instead of copying and pasting text and manually downloading images, Nuanta connects directly to your static site pipeline. When you click "Publish" in Nuanta, it fires a webhook payload to GitHub.

This repository includes the necessary workflow file (`.github/workflows/new-article.yml`) to catch that webhook. When triggered, the workflow:

1. Downloads the high-resolution cover image into `public/blog-images/`.
2. Generates a new Markdown (`.md`) file inside `src/content/blog/` mapping the payload into Astro frontmatter.
3. Commits both files and pushes them automatically to your `main` branch.
4. Your existing hosting provider (Vercel, Netlify, Cloudflare Pages, etc.) picks up the commit and rebuilds your site.

### 📖 Full Documentation
For a detailed step-by-step guide on setting up the GitHub Token and creating the integration in Nuanta, read the official guide:

👉 [**Auto-Publish to Your Static Site (Astro, Gatsby, Hugo)**](https://nuanta.io/docs/how-to-publish-to-astro/)

---

## Running this Astro Site Locally

This repository uses the standard Astro Blog template under the hood to demonstrate where files go.

1. **Install dependencies:**  
   `npm install`
2. **Start the local server:**  
   `npm run dev`
3. **View the site:**  
   Open `http://localhost:4321` in your browser.

Astro automatically routes Content Collection entries from `src/content/blog/` into fully-styled pages.
