---
name: seo
description: Audit, plan, and implement SEO improvements covering technical SEO, on-page optimization, structured data, Core Web Vitals, and content strategy. Use when the user wants to improve search rankings, fix crawlability issues, optimize meta tags, add schema markup, or conduct keyword research.
origin: ECC
---

# SEO

Improve search visibility through technical correctness, content relevance, and performance — not tricks.

## When to Activate

- auditing a site for technical SEO issues (crawlability, indexability, canonicalization)
- optimizing meta titles, descriptions, and heading structure
- adding or validating structured data (JSON-LD schema markup)
- improving Core Web Vitals (LCP, INP, CLS)
- conducting keyword research and mapping keywords to pages
- planning internal linking structure
- generating or validating sitemaps and robots.txt
- reviewing content for on-page SEO quality

## Core Rules

1. Fix technical blockers before content work — a crawl error negates every other effort.
2. Every page needs one clear target keyword; avoid keyword cannibalization.
3. Title tags: 50–60 characters, include primary keyword near the front.
4. Meta descriptions: 120–160 characters, action-oriented, include keyword naturally.
5. One `<h1>` per page, aligned to the target keyword and page intent.
6. Prefer long-term signals (E-E-A-T, links, content depth) over manipulative patterns.
7. Mobile-first — Google indexes the mobile version.

## Technical SEO Checklist

### Crawlability
- [ ] `robots.txt` allows important pages; disallows staging, admin, search results
- [ ] No important pages blocked by noindex
- [ ] Internal links reachable within 3 clicks from the homepage
- [ ] No redirect chains longer than 2 hops
- [ ] Canonical tags are self-referencing where appropriate; no canonical loops

### Indexability
- [ ] `<meta name="robots" content="index, follow">` on all important pages
- [ ] Canonical points to the preferred URL (https, www/non-www consistent)
- [ ] Hreflang set correctly for multilingual sites
- [ ] Sitemap submitted to Google Search Console and Bing Webmaster Tools

### Performance (Core Web Vitals)
- [ ] LCP (Largest Contentful Paint) < 2.5s
- [ ] INP (Interaction to Next Paint) < 200ms
- [ ] CLS (Cumulative Layout Shift) < 0.1
- Common fixes: preload hero image, remove render-blocking scripts, reserve space for images/ads

### Structured Data
- [ ] Organization or LocalBusiness schema on homepage
- [ ] Article or BlogPosting schema on editorial content
- [ ] Product + Offer schema on product pages
- [ ] BreadcrumbList on all interior pages
- [ ] FAQ schema where Q&A sections exist
- [ ] Validate via Google Rich Results Test

## On-Page Optimization

### Title Tag Formula
```
Primary Keyword - Secondary Modifier | Brand Name
```
Example: `Next.js Performance Optimization - Speed Guide | Acme`

### Meta Description Formula
```
[Action verb] [primary keyword] [value proposition]. [Supporting detail]. [Soft CTA].
```
Example: `Improve your Next.js performance with proven optimization techniques. Covers bundle splitting, image optimization, and caching. Free guide.`

### Heading Structure
```
H1: target keyword + intent (one per page)
  H2: major subtopics
    H3: supporting details under each H2
```

### Content Depth Signals
- Cover the topic completely — check top-ranking competitors for missing subtopics
- Use semantic variants and related terms naturally (LSI keywords)
- Include original data, examples, or insights not found elsewhere
- Update stale content — freshness is a ranking factor for news and volatile queries

## Keyword Research Workflow

1. **Seed keywords** — brainstorm core terms from the product/service
2. **Expand** — use tools (Ahrefs, SEMrush, Google Search Console, Keywords Everywhere) to find variations, questions, and related terms
3. **Classify by intent**:
   - Informational: "how to", "what is", "guide" → blog/docs
   - Navigational: brand/product names → homepage, product pages
   - Commercial: "best", "vs", "review" → comparison/landing pages
   - Transactional: "buy", "pricing", "demo" → conversion pages
4. **Prioritize** by: search volume × intent match × competition (KD)
5. **Map** one primary keyword per URL — avoid cannibalization

## Internal Linking

- Link from high-authority pages (homepage, top posts) to pages you want to rank
- Use descriptive anchor text matching the target keyword of the destination page
- Avoid generic anchors: "click here", "read more", "this article"
- Add links from new content to existing relevant pages
- Use breadcrumbs on all interior pages

## Schema Markup Examples

### Article
```json
{
  "@context": "https://schema.org",
  "@type": "Article",
  "headline": "Page Title Here",
  "author": { "@type": "Person", "name": "Author Name" },
  "datePublished": "2024-01-15",
  "dateModified": "2024-03-01",
  "publisher": {
    "@type": "Organization",
    "name": "Brand Name",
    "logo": { "@type": "ImageObject", "url": "https://example.com/logo.png" }
  }
}
```

### BreadcrumbList
```json
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    { "@type": "ListItem", "position": 1, "name": "Home", "item": "https://example.com" },
    { "@type": "ListItem", "position": 2, "name": "Blog", "item": "https://example.com/blog" },
    { "@type": "ListItem", "position": 3, "name": "Article Title", "item": "https://example.com/blog/article" }
  ]
}
```

### FAQ
```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "What is the question?",
      "acceptedAnswer": { "@type": "Answer", "text": "The answer text here." }
    }
  ]
}
```

## Common Anti-Patterns

Avoid these — they hurt rankings or risk manual penalties:

- Keyword stuffing in titles, headings, or body text
- Thin content (< 300 words with no unique value)
- Duplicate content across URLs without canonical tags
- Hidden text or links
- Buying links from link farms
- Auto-generated content without review
- Cloaking (showing different content to bots vs users)
- Exact-match anchor text overuse in link building

## Audit Output Format

When delivering an SEO audit, structure as:

1. **Critical issues** — blocking crawl, index, or core signals (fix immediately)
2. **High-impact opportunities** — likely to improve rankings within 1–3 months
3. **Quick wins** — low-effort, measurable improvements
4. **Content gaps** — missing pages or topics competitors rank for
5. **Recommendations** — prioritized action list with owner and effort estimate

## Quality Gate

Before delivering any SEO work:
- all recommendations link to the specific page or element affected
- no conflicting advice (e.g., noindex on a page you want to rank)
- structured data passes Google Rich Results Test
- title and meta lengths checked against character limits
- no pattern recommendations that violate Google's Search Essentials
