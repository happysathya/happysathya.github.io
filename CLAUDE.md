# Technical Blog - GitHub Pages

This is a static technical blog hosted on GitHub Pages at `happysathya.github.io`.

## Structure

- `index.html` - Blog index with search functionality
- Individual HTML files for each post (e.g., `the-juke-joint-had-a-door.html`)
- `robots.txt` - Crawler permissions, points to sitemap
- `sitemap.xml` - Lists all pages for search engine indexing

## Search Setup

The blog uses simple client-side substring search (no external dependencies).

- Searches across `title`, `excerpt`, and `tag` fields
- Case-insensitive
- Multiple search terms must ALL match (e.g., "claude skills" finds posts containing both words)

## Adding a New Blog Entry

1. Create the HTML file for your post (e.g., `my-new-post.html`)
2. Add a "← Blog" link in the footer pointing back to `index.html`
3. Add an entry to the `posts` array in `index.html`:

```javascript
const posts = [
    {
        url: 'my-new-post.html',
        date: 'Jan 2026',
        tag: 'Topic',
        title: 'Post Title',
        excerpt: 'A brief description of the post content.'
    },
    // ... existing posts
];
```

4. Add SEO meta tags in the `<head>` of the new post:

```html
<meta name="description" content="Brief description for search results.">
<link rel="canonical" href="https://happysathya.github.io/my-new-post.html">
<meta property="og:type" content="article">
<meta property="og:title" content="Post Title">
<meta property="og:description" content="Brief description for search results.">
<meta property="og:url" content="https://happysathya.github.io/my-new-post.html">
```

5. Add the new URL to `sitemap.xml`

### Post Object Fields

| Field | Description |
|-------|-------------|
| `url` | Filename of the post HTML file |
| `date` | Display date (e.g., "Jan 2026") |
| `tag` | Category/topic tag (displayed in blue) |
| `category` | Either `'technical'` or `'personal'` — used for filter buttons on the index |
| `title` | Full post title |
| `excerpt` | 1-2 sentence summary for the card |

## SEO

All pages include:
- `<meta name="description">` for search result snippets
- `<link rel="canonical">` to prevent duplicate content
- Open Graph tags (`og:type`, `og:title`, `og:description`, `og:url`) for social sharing
- `robots.txt` and `sitemap.xml` at the repo root

## Styling

Posts use a dark modern theme with:
- Background: `#0f0f12`
- Font: Plus Jakarta Sans (body), JetBrains Mono (code/meta)
- Accent colors: Orange (`#ff7b54`), Blue (`#5a9fff`), Purple (`#b490ff`)
