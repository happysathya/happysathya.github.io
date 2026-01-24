# Technical Blog - GitHub Pages

This is a static technical blog hosted on GitHub Pages at `happysathya.github.io`.

## Structure

- `index.html` - Blog index with search functionality
- Individual HTML files for each post (e.g., `claude-code-extensibility-guide.html`)

## Search Setup

The blog uses [Fuse.js](https://www.fusejs.io/) for client-side fuzzy search. The library is loaded via CDN:

```html
<script src="https://cdn.jsdelivr.net/npm/fuse.js@7.0.0"></script>
```

Search is configured to match against `title`, `excerpt`, and `tag` fields with a threshold of 0.4 (lower = stricter matching).

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

### Post Object Fields

| Field | Description |
|-------|-------------|
| `url` | Filename of the post HTML file |
| `date` | Display date (e.g., "Jan 2025") |
| `tag` | Category/topic tag (displayed in blue) |
| `title` | Full post title |
| `excerpt` | 1-2 sentence summary for the card |

## Styling

Posts use a dark modern theme with:
- Background: `#0f0f12`
- Font: Plus Jakarta Sans (body), JetBrains Mono (code/meta)
- Accent colors: Orange (`#ff7b54`), Blue (`#5a9fff`), Purple (`#b490ff`)
