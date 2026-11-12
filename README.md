# Documents Without Borders - Website + RSS Feed

Ready to upload to GitHub. Already configured for https://documentswithoutborders.org

## What's Inside
- `index.html` - Homepage with RSS autodiscovery + Subscribe button, already branded
- `generate-rss.js` - Generates feed.xml from posts.json (already set to your domain)
- `posts.json` - EDIT THIS to add your real posts. 3 starter posts included - replace them.
- `public/feed.xml` + `feed.xml` - Your live feed, already generated
- `package.json` - `npm run generate-rss`

## Your Feed URL
https://documentswithoutborders.org/feed.xml

## How to Upload to GitHub
1. Go to github.com > New Repository > name it `documentswithoutborders` (or your existing repo)
2. Click "uploading an existing file" and drag ALL files from this folder
3. Commit

If you already have a repo / website repo:
- Just copy `generate-rss.js`, `posts.json`, `feed.xml` into the root of that repo
- And copy the RSS <link> line from index.html into your real site's <head>:
  <link rel="alternate" type="application/rss+xml" title="Documents Without Borders - RSS Feed" href="https://documentswithoutborders.org/feed.xml" />

## How to Add a New Blog Post
1. Add a new object at the TOP of `posts.json`:
{
  "title": "Your New Post Title",
  "link": "https://documentswithoutborders.org/blog/your-post-slug",
  "description": "One sentence summary.",
  "date": "Fri, 13 Nov 2026 12:00:00 GMT",
  "guid": "https://documentswithoutborders.org/blog/your-post-slug"
}
Tip: Get the date format with `new Date().toUTCString()` in your browser console.

2. Run:
   npm run generate-rss
3. Commit + push to GitHub - your feed updates automatically.

## Test It
1. Open https://documentswithoutborders.org/feed.xml in browser
2. Validate at https://validator.w3.org/feed/
3. Add it to Feedly - your 3 posts should show up.
