# Minimal Modern Template - Design Specification

> Suitable for startup pitches, tech product presentations, project introductions, modern business presentations.

---

## I. Template Overview

| Property       | Description                                            |
| -------------- | ------------------------------------------------------ |
| **Template Name** | minimal_modern                                    |
| **Use Cases**  | Startup pitches, tech product launches, project introductions, modern business presentations |
| **Design Tone** | Minimal, clean, professional, modern, content-focused |
| **Theme Mode** | Light theme (white background + near-black text + blue accent) |

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
| **Primary Near-Black** | `#111827` | Main text, titles |
| **Secondary Slate** | `#4B5563` | Body text, secondary elements |
| **Accent Blue** | `#3B82F6` | Accents, highlights, decorations |
| **Background White** | `#FFFFFF` | Page main background           |

### Text Colors

| Role           | Value       | Usage                  |
| -------------- | ----------- | ---------------------- |
| **Dark Text** | `#111827`   | Primary titles, headings |
| **Body Text** | `#4B5563`   | Body content           |
| **Muted Text** | `#6B7280` | Descriptions, annotations |
| **Light Gray** | `#9CA3AF`  | Footer, auxiliary info |

### Neutral Colors

| Role           | Value       | Usage                  |
| -------------- | ----------- | ---------------------- |
| **Background Alt** | `#F9FAFB`   | Alternative background, card backgrounds |
| **Border Gray** | `#E5E7EB`  | Borders, dividers |

### Functional Colors

| Usage      | Value       | Description    |
| ---------- | ----------- | -------------- |
| **Success** | `#10B981`  | Positive indicators |
| **Warning** | `#EF4444`  | Alerts         |
| **Info**   | `#6366F1`   | Information tips |

---

## IV. Typography System

### Font Stack

**Font Stack**: `"SF Pro Display", -apple-system, BlinkMacSystemFont, "PingFang SC", "Hiragino Sans GB", "Microsoft YaHei", "Segoe UI", sans-serif`

### Font Size Hierarchy (updated for modern aesthetics)

| Level | Usage            | Size | Weight  | Line Height |
| ----- | ---------------- | ---- | ------- | ---------- |
| H1    | Cover main title | 56px | Bold    | 1.2 |
| H2    | Page title       | 32px | Bold    | 1.3 |
| H3    | Section title    | 28px | Semi-bold | 1.3 |
| H4    | Card title       | 24px | Semi-bold | 1.3 |
| P     | Body content     | 16px | Regular | 1.6 |
| High  | Highlighted data | 36px | Bold    | 1.2 |
| Sub   | Notes/sources    | 12px | Regular | 1.5 |
| XS    | Page number/copyright | 10px | Regular | 1.5 |

---

## V. Page Structure

### General Layout

| Area           | Position/Height | Description                            |
| -------------- | --------------- | -------------------------------------- |
| **Left Accent Bar** | x=80, width=4px | Left vertical accent stripe in primary blue |
| **Content Area** | x: 88-1200, y: 70-650 | Main content area with generous white space |

### Decorative Elements

- **Left Accent Stripe**: Accent blue (`#3B82F6`), width 4px, vertical decoration
- **Subtle Geometric Decorations**: Low-opacity circles/squares in corners (not distracting from content)

---

## VI. Page Types

### 1. Cover Page (01_cover.svg)

- White background
- Left accent stripe
- Left-aligned main title (large bold)
- Subtitle below title in muted gray
- Bottom-left: presenter/institution info
- Bottom-right: optional logo area

### 2. Table of Contents Page (02_toc.svg)

- White background
- Left accent stripe
- Large page title at top
- Single-column list of TOC items
- Each item: number + title, clean spacing

### 3. Chapter Page (02_chapter.svg)

- White background
- Large chapter title left-aligned
- Minimal decorative geometric shapes in accent blue at low opacity
- Chapter description below title in muted gray

### 4. Content Page (03_content.svg)

- White background
- Left accent stripe
- Page title at top
- Flexible content area below title
- Footer with page number

### 5. Ending Page (04_ending.svg)

- White background
- Left accent stripe
- Large centered "Thank You" title
- Contact info card at bottom
- Minimal decorative elements

---

## VII. Layout Patterns

| Pattern            | Use Cases                      |
| ------------------ | ------------------------------ |
| **Single Column Full Width** | Content discussion, key insights |
| **Two-Column Cards** | Feature lists, comparison            |
| **Left-Right Split (5:5)** | Image-text mixed layout      |
| **Left-Right Split (4:6)** | Image + narrative      |
| **Card Grid**      | Feature grid, team list           |

---

## VIII. Spacing Guidelines (8px grid)

| Element            | Value  |
| ------------------ | ------ |
| Card gap           | 24px   |
| Content block gap  | 32px   |
| Card padding       | 28px   |
| Card border radius | 12px    |
| Icon-to-text gap   | 16px   |
| Title-to-content gap | 48px |

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

Templates use `{{PLACEHOLDER}}` format placeholders. Common placeholders:

| Placeholder        | Description        |
| ------------------ | ------------------ |
| `{{TITLE}}`        | Project main title |
| `{{SUBTITLE}}`     | Subtitle           |
| `{{AUTHOR}}`       | Presenter name     |
| `{{INSTITUTION}}`  | Company/institution |
| `{{DATE}}`         | Presentation date       |
| `{{PAGE_TITLE}}`   | Page title         |
| `{{CHAPTER_TITLE}}`| Chapter title      |
| `{{CHAPTER_DESC}}` | Chapter description |
| `{{KEY_MESSAGE}}`  | Key message        |
| `{{PAGE_NUM}}`     | Page number        |
| `{{SECTION_NAME}}` | Section name (footer) |
| `{{THANK_YOU}}`    | Thank-you message  |
| `{{CONTACT_INFO}}` | Contact information |

---

## XI. Component Specifications

### 1. Card

```xml
<!-- Standard card with soft shadow -->
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
<rect x="80" y="120" width="520" height="280" rx="12" fill="#FFFFFF" filter="url(#softShadow)"/>
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
