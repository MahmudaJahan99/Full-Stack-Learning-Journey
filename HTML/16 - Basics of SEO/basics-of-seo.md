# Basics of SEO

**SEO** stands for **Search Engine Optimization**. SEO is the practice of improving a website so that search engines can better **understand, discover, and present its content** to users. The goal is not simply to rank higher, but to make useful content easier for the right people to find.

## How Search Engines Work

Search engines generally perform three major processes:

### 1. Crawling

Search engines use automated programs, commonly called **crawlers**, to discover web pages.

### 2. Indexing

The discovered content can be analyzed and stored in the search engine's index.

### 3. Ranking

When someone performs a search, the search engine determines which relevant pages should appear and in what order.

---

## ✓ Use a Meaningful `<title>`

The `<title>` element provides the title of a web page. A useful title helps users and search engines understand what the page is about.

```html
<head>
  <title>Jane's Frontend Projects</title>
</head>
```

## ✓ Meta Description

A meta description provides a short summary of a page. Search engines may use this information when displaying a page in search results.

```html
<meta
  name="description"
  content="Explore frontend projects built with React, JavaScript, and modern web technologies."
/>
```

A good description should be:

- Relevant to the page
- Clear
- Concise
- Useful to potential visitors

## ✓ Heading Structure

Headings help communicate the structure and topic of a page.

```html
<h1>Frontend Development</h1>

<h2>Projects</h2>

<h2>Skills</h2>

<h2>Contact</h2>
```

The `<h1>` should describe the primary topic of the page. Use `<h2>`, `<h3>`, and other heading levels to organize subsections logically.

## ✓ Semantic HTML

Semantic HTML helps communicate the meaning and structure of content. Choose elements that describe the purpose of the content. This can help search engines better understand the structure of a page.

## ✓ SEO-Friendly URLs

URLs should be understandable and descriptive. A clear URL gives users and search engines useful information about the page.

Prefer:

```text
example.com/blog/html-semantic-elements
```

## ✓ Image Optimization

Images should be optimized for both users and search engines. Use meaningful file names and provide appropriate alternative text.

```html
<img
  src="react-dashboard.png"
  alt="React dashboard displaying sales statistics"
/>
```

Large, unoptimized images can also negatively affect page performance.

## ✓ Quality Content

SEO is not only about adding keywords.

Useful content should be:

- Relevant
- Helpful
- Original
- Easy to understand
- Written for people

Avoid filling a page with keywords unnaturally.

## ✓ Internal Links

Internal links connect pages within the same website. They help users discover related content and help search engines understand relationships between pages.

```html
<a href="/projects"> View Projects </a>
```

## ✓ Mobile-Friendly Websites

A large portion of web traffic comes from mobile devices. Websites should therefore work well across different screen sizes. Mobile usability contributes to a better overall user experience.

Important considerations include:

- Responsive layouts
- Readable text
- Touch-friendly controls
- Fast loading
- No unnecessary horizontal scrolling

## ✓ Page Performance

Website performance can affect both user experience and search visibility. A fast website generally provides a better experience for users.

Good practices include:

- Optimizing images
- Reducing unnecessary JavaScript
- Minimizing large resources
- Using efficient CSS
- Avoiding unnecessary network requests
- Using caching where appropriate

---

## `robots.txt`

A `robots.txt` file can provide instructions to search-engine crawlers about which URLs they should or should not crawl.

Example:

```text
User-agent: *
Disallow: /private/
```

`robots.txt` is a crawling instruction mechanism. It should **not** be treated as a way to securely hide sensitive information.

---

## Sitemap

A **sitemap** provides information about the URLs that are important on a website.

A common sitemap file is:

```text
sitemap.xml
```

It can help search engines discover pages, especially on larger or more complex websites.
