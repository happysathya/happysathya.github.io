---
name: blog-template
description: >
  Creates blog posts with consistent dark theme styling. Use when: creating
  a blog post, converting markdown to HTML blog post, writing an article,
  making a new post, or any blog/post creation for happysathya.github.io.
allowed-tools: "Read,Write,Edit"
user-invocable: true
---

# Blog Post Template Skill

Use this design system when creating new blog posts for happysathya.github.io.

## Design Tokens

### Colors (CSS Variables)
```css
--bg-primary: #0f0f12;      /* Main background */
--bg-secondary: #18181d;    /* Cards, diagrams */
--bg-tertiary: #1f1f26;     /* Elevated elements */
--bg-code: #13131a;         /* Code blocks */
--text-primary: #e8e8ed;    /* Headings, emphasis */
--text-secondary: #9898a6;  /* Body text */
--text-muted: #6b6b7a;      /* Captions, hints */
--accent-orange: #ff7b54;   /* Primary accent, links */
--accent-blue: #5a9fff;     /* Secondary accent, tags */
--accent-purple: #b490ff;   /* Tertiary accent */
--accent-green: #5ce0a8;    /* Success, checks */
--accent-yellow: #ffd15c;   /* Warnings, annotations */
--accent-pink: #ff8ab5;     /* Errors, crosses */
--border-color: #2a2a35;    /* Visible borders */
--border-subtle: #232330;   /* Subtle dividers */
```

### Typography
- **Body Font**: 'Plus Jakarta Sans', sans-serif
- **Code Font**: 'JetBrains Mono', monospace
- **Base Size**: 15px
- **Line Height**: 1.7

### Google Fonts Import
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600&family=Plus+Jakarta+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
```

## HTML Structure

### Basic Template
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{POST_TITLE}</title>
    <!-- Google Fonts -->
    <!-- CSS Variables and Styles -->
</head>
<body>
    <div class="container">
        <nav style="margin-bottom: 30px;">
            <a href="index.html" style="color: var(--accent-orange); text-decoration: none; font-size: 0.9rem;">← Blog</a>
        </nav>

        <header>
            <h1>{GRADIENT_TITLE}</h1>
            <p class="subtitle">{SUBTITLE}</p>
        </header>

        <!-- Sections -->
        <section id="{section-id}">
            <h2>{Section Title}</h2>
            <!-- Content -->
        </section>

        <footer>
            <p><a href="index.html" style="color: var(--accent-orange); text-decoration: none;">← Blog</a></p>
            <p>Created by <a href="https://happysathya.com" target="_blank" style="color: var(--accent-blue); text-decoration: none;">Sathya</a> • <a href="https://www.linkedin.com/in/happysathya/" target="_blank" style="color: var(--accent-blue); text-decoration: none;">LinkedIn</a></p>
            <p>Generated with Claude • {MONTH} {YEAR}</p>
        </footer>
    </div>
</body>
</html>
```

## Component Patterns

### Container
```css
.container {
    max-width: 900px;
    margin: 0 auto;
    padding: 60px 40px;
}
```

### Header with Gradient Title
```css
header h1 {
    font-size: 2.8rem;
    font-weight: 700;
    letter-spacing: -0.03em;
    background: linear-gradient(135deg, var(--accent-orange), var(--accent-purple));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
}
```

### Section Headers (h2 with accent bar)
```css
h2 {
    font-size: 1.6rem;
    font-weight: 700;
    display: flex;
    align-items: center;
    gap: 12px;
}
h2::before {
    content: '';
    display: inline-block;
    width: 4px;
    height: 28px;
    background: var(--accent-orange);
    border-radius: 2px;
}
```

### Code Blocks
```css
.code-block {
    background: var(--bg-code);
    border: 1px solid var(--border-color);
    border-radius: 10px;
    overflow: hidden;
}
.code-header {
    background: var(--bg-tertiary);
    padding: 10px 18px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 0.75rem;
    color: var(--text-muted);
    border-bottom: 1px solid var(--border-color);
}
```

### Diagrams/Cards
```css
.diagram {
    background: var(--bg-secondary);
    border: 1px solid var(--border-color);
    border-radius: 12px;
    padding: 35px;
    margin: 30px 0;
}
```

### Tables
```css
.table-wrapper {
    overflow-x: auto;
    border-radius: 10px;
    border: 1px solid var(--border-color);
}
thead { background: var(--bg-tertiary); }
th { padding: 14px 18px; font-weight: 600; }
td { padding: 12px 18px; color: var(--text-secondary); }
tbody tr:hover { background: var(--bg-secondary); }
```

### Syntax Highlighting Classes
```css
.code-comment { color: var(--text-muted); }
.code-keyword { color: var(--accent-purple); }
.code-string { color: var(--accent-green); }
.code-property { color: var(--accent-blue); }
.code-value { color: var(--accent-orange); }
.code-annotation { color: var(--accent-yellow); }
```

## After Creating a Post

Remember to add an entry to the `posts` array in `index.html`:

```javascript
{
    url: 'new-post.html',
    date: 'Mon YYYY',
    tag: 'Topic',
    title: 'Post Title',
    excerpt: 'Brief description.'
}
```

## Reference

For the complete CSS implementation, see:
- `{baseDir}/references/base-styles.css` - Full CSS stylesheet
- Existing post: `/Users/sathya/projects/happysathya/happysathya.github.io/claude-code-extensibility-guide.html`
