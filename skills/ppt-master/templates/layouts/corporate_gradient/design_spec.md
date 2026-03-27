# Corporate Gradient Template - Design Specification

> Suitable for business annual reports, executive briefings, corporate strategy reviews, high-stakes business presentations.

---

## I. Template Overview

| Property       | Description                                            |
| -------------- | ------------------------------------------------------ |
| **Template Name** | corporate_gradient                                    |
| **Use Cases**  | Annual reports, executive briefings, strategy reviews, corporate updates |
| **Design Tone** | Premium corporate, modern executive, confident, professional |
| **Theme Mode** | Deep navy gradient background + white/light content cards |

---

## II. Canvas Specification

| Property       | Value                         |
| -------------- | ----------------------------- |
| **Format**     | Standard 16:9                 |
| **Dimensions** | 1280 × 720 px                |
| **viewBox**    | `0 0 1280 720`                |
| **Page Margins** | Left/Right 80px, Top/Bottom 70px |
| **Safe Area**  | x: 80-1200, y: 70-650        |

---

## III. Color Scheme

### Primary Colors

| Role           | Value       | Notes                            |
| -------------- | ----------- | -------------------------------- |
| **Deep Navy** | `#0F172A` | Background gradient base |
| **Slate Navy** | `#1E293B` | Secondary background, card shadows |
| **Indigo Accent** | `#6366F1` | Primary accent color |
| **Violet Accent** | `#8B5CF6` | Secondary accent color |

### Text Colors

| Role           | Value       | Usage                  |
| -------------- | ----------- | ---------------------- |
| **Dark Text** | `#0F172A`   | On light backgrounds |
| **Body Text** | `#334155`   | Body content on white |
| **Muted Text** | `#64748B` | Descriptions |
| **Light Text** | `#F8FAFC`   | Text on dark backgrounds |
| **Border Gray** | `#E2E8F0` | Borders |

### Gradient Background

Cover and chapter pages use vertical gradient from top:
- Start: `#0F172A` (deep navy)
- Middle: `#1E293B` (slate navy)
- End: `#0F172A` (deep navy)

### Functional Colors

| Usage      | Value       | Description    |
| ---------- | ----------- | -------------- |
| **Success** | `#10B981`  | Positive indicators |
| **Warning** | `#EF4444`  | Alerts         |

---

## IV. Typography System

### Font Stack

**Font Stack**: `"SF Pro Display", -apple-system, BlinkMacSystemFont, "PingFang SC", "Hiragino Sans GB", "Microsoft YaHei", "Segoe UI", sans-serif`

### Font Size Hierarchy

| Level | Usage            | Size | Weight  | Line Height |
| ----- | ---------------- | ---- | ------- | ---------- |
| H1    | Cover main title | 56px | Bold    | 1.2 |
| H2    | Page title       | 32px | Bold    | 1.3 |
| H3    | Card title       | 24px | Semi-bold | 1.3 |
| P     | Body content     | 16px | Regular | 1.6 |
| High  | Highlighted data | 36px | Bold    | 1.2 |
| Sub   | Notes/sources    | 12px | Regular | 1.5 |
| XS    | Page number/copyright | 10px | Regular | 1.5 |

---

## V. Page Structure

### Design Philosophy

- Deep dark gradient background on cover and chapter pages for premium executive feel
- Clean white cards with soft drop shadows for content
- Generous white space inside cards
- Indigo/violet gradient accents for modern corporate look

---

## VI. Page Types

### 1. Cover Page (01_cover.svg)

- Vertical gradient background (deep navy)
- Centered content: logo, title, subtitle
- Bottom: presenters, institution, date
- Subtle gradient accents

### 2. Table of Contents Page (02_toc.svg)

- White background
- Two-column card layout
- Each TOC item in shadowed white card
- Number + title on colored accent bar

### 3. Chapter Page (02_chapter.svg)

- Full page gradient background
- Centered white chapter title with glow
- Subtitle description below in light text

### 4. Content Page (03_content.svg)

- Gradient top header bar with page title (white text)
- Content area below with white background
- Content goes in shadowed cards with proper spacing

### 5. Ending Page (04_ending.svg)

- Gradient background matching cover
- Centered "Thank You" title
- Contact info card at bottom

---

## VII. Layout Patterns

| Pattern            | Use Cases                      |
| ------------------ | ------------------------------ |
| **Three-card grid** | Key metrics overview            |
| **Two-column cards** | Key points list            |
| **Full-width card** | Main content block      |
| **Image + text card** | Hero content with narrative |

---

## VIII. Spacing Guidelines (8px grid)

| Element            | Value  |
| ------------------ | ------ |
| Card gap           | 24px   |
| Card padding       | 32px   |
| Card border radius | 16px    |
| Card shadow | soft filter (stdDev 8, opacity 0.08) |
| Title-to-content gap | 64px |

---

## IX. SVG Technical Constraints

### Mandatory Rules

1. viewBox: `0 0 1280 720`
2. Use `<rect>` elements for backgrounds
3. Use `<tspan>` for text wrapping (no `<foreignObject>`)
4. Use `fill-opacity` / `stroke-opacity` for transparency; no `rgba()`
5. Prohibited: `clipPath`, `mask`, `<style>`, `class`, `foreignObject`
6. Prohibited: `textPath`, `animate*`, `script`, `marker`/`marker-end`
7. Use `<polygon>` triangles for arrows instead of `<marker>`

### PPT Compatibility Rules

- No `<g opacity="...">` (group opacity); set opacity on each child element individually
- Use overlay layers for image transparency
- Inline styles only; no external CSS or `@font-face`

---

## X. Placeholder Specification

Templates use `{{PLACEHOLDER}}` format placeholders:

| Placeholder        | Description        |
| ------------------ | ------------------ |
| `{{TITLE}}`        | Presentation main title |
| `{{SUBTITLE}}`     | Presentation subtitle |
| `{{COMPANY_LOGO}}` | Company logo area |
| `{{AUTHOR}}`       | Presenter name     |
| `{{INSTITUTION}}`  | Company/institution |
| `{{DATE}}`         | Presentation date       |
| `{{PAGE_TITLE}}`   | Page title         |
| `{{CHAPTER_TITLE}}`| Chapter title      |
| `{{THANK_YOU}}`    | Thank-you message  |
| `{{CONTACT_INFO}}` | Contact information |

---

## XI. Component Specifications

### Card with Shadow

```xml
<defs>
  <filter id="softShadow" x="-15%" y="-15%" width="140%" height="140%">
    <feGaussianBlur in="SourceAlpha" stdDeviation="8"/>
    <feOffset dx="0" dy="4" result="offsetBlur"/>
    <feFlood flood-color="#000000" flood-opacity="0.08" result="shadowColor"/>
    <feComposite in="shadowColor" in2="offsetBlur" operator="in" result="shadow"/>
    <feMerge>
      <feMergeNode in="shadow"/>
      <feMergeNode in="SourceGraphic"/>
    </feMerge>
  </filter>
</defs>
<rect x="80" y="140" width="1040" height="400" rx="16" fill="#FFFFFF" filter="url(#softShadow)"/>
```

---

## XII. Usage Instructions

1. Copy the template to the project directory
2. Select the appropriate page template based on content needs
3. Use placeholders to mark content that needs replacement
4. Generate the final SVG through the Executor role

---

## XIII. Design Checklist

### Before Generation

- [ ] Is the content suitable for the current page layout
- [ ] Does the color scheme follow the specification
- [ ] Is the font size hierarchy correct

### After Generation

- [ ] viewBox = `0 0 1280 720`
- [ ] No prohibited elements
- [ ] Text is readable (≥12px)
- [ ] Content is within the safe area
- [ ] Elements are properly aligned to 8px grid
- [ ] Style consistency check passed
