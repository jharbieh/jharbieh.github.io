# jharbieh.github.io

## Migrating Blog Posts from WordPress to GitHub Pages

This guide explains how to move your WordPress blog posts to a GitHub Pages site (username.github.io) using Jekyll and Markdown.

---

### Ensuring Your GitHub Pages Site Uses Jekyll

GitHub Pages uses Jekyll by default if your repository contains a `_config.yml` file or a `_posts` directory.  
To explicitly use Jekyll:

1. Make sure your repository has a `_config.yml` file in the root directory (even if it's empty).
2. Do **not** include a file named `.nojekyll` in the root—this file disables Jekyll processing.
3. Add your Markdown posts to the `_posts` directory.

You can verify Jekyll is being used if your site processes Markdown, uses layouts, and supports Liquid templating.

---

### 1. Export Content from WordPress

1. Log in to your WordPress dashboard.
2. Go to **Tools > Export**.
3. Select **All Content** (or choose specific posts/pages).
4. Click **Download Export File** to get an XML file.

---

### 2. Convert WordPress XML to Markdown

GitHub Pages (with Jekyll) uses Markdown files. Convert your XML export to Markdown using one of these methods:

- **WordPress-to-Jekyll Exporter plugin**:  
  Install the plugin on your WordPress site and export posts as Markdown with YAML front matter.
- **External tools**:  
  Use [ExitWP](https://github.com/thomasf/exitwp) or [Pandoc](https://pandoc.org/) to convert XML to Markdown.

---

### 3. Set Up Your GitHub Pages Repository

1. Create a repository named `username.github.io` (replace `username` with your GitHub username).
2. Clone it to your local machine:
   ```
   git clone https://github.com/username/username.github.io
   cd username.github.io
   ```

---

### 4. Add Blog Posts

1. Copy the converted Markdown files into the `_posts` directory.
2. Ensure each file is named: `YYYY-MM-DD-title.md`
3. Each file should start with YAML front matter, for example:
   ```
   ---
   layout: post
   title: "My First Blog Post"
   date: 2025-07-20
   categories: [blog, tutorial]
   ---
   ```

---

### 5. Commit and Push Changes

```
git add .
git commit -m "Add blog posts from WordPress"
git push origin main
```

---

### 6. Test Your GitHub Pages Site

- Visit `https://username.github.io` to see your blog live.

---

### Tips

- If using a custom Jekyll theme, configure it in `_config.yml`.
- For troubleshooting, check the [GitHub Pages documentation](https://docs.github.com/en/pages) and your repository's Actions tab for build errors.

---