# Monochrome Pro Template - Design Specification

> Suitable for architecture portfolios, design showcases, high-end brand presentations, professional photography displays. Strict grid layout, monochrome minimalist aesthetic with single accent color.

---

## I. Template Overview

| Property       | Description                                            |
| -------------- | ------------------------------------------------------ |
| **Template Name** | monochrome_pro                                    |
| **Use Cases**  | Architecture/design portfolios, high-end brand showcases, photography exhibitions, minimal graphic design |
| **Design Tone** | Minimalist, professional, high-contrast, precise, sophisticated |
| **Theme Mode** | Light monochrome (white background + black/gray hierarchy + one accent color) |

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

## III. Color Scheme (Monochrome Palette)

### Primary Monochrome

| Role           | Value       | Notes                            |
| -------------- | ----------- | -------------------------------- |
| **Pure Black** | `#000000` | Primary text, main headings     |
| **Dark Gray**  | `#222222` | Secondary headings, body text   |
| **Medium Gray**| `#555555` | Muted body text, descriptions    |
| **Light Gray** | `#AAAAAA` | Borders, dividers, auxiliary    |
| **Ultra Light**| `#F0F0F0` | Card backgrounds, subtle areas  |
| **Pure White** | `#FFFFFF` | Main page background           |
| **Accent**     | `{{ACCENT_COLOR}}` | Single accent color (customizable) for highlights, key points |

### Text Colors (Monochrome Hierarchy)

| Role           | Value       | Usage                  |
| -------------- | ----------- | ---------------------- |
| **Black Text** | `#000000`   | H1/H2 main headings, primary content |
| **Dark Text** | `#222222`   | Body content, secondary headings |
| **Muted Text** | `#555555` | Descriptions, annotations |
| **Light Text** | `#AAAAAA` | Footer, auxiliary info |
| **White Text** | `#FFFFFF`   | Text on dark backgrounds |

---

## IV. Typography System

### Font Stack

**Font Stack**: `"SF Pro Display\", -apple-system, BlinkMacSystemFont, \"PingFang SC\", \"Hiragino Sans GB\", \"Microsoft YaHei\", \"Segoe UI\", sans-serif`

### Font Size Hierarchy

| Level | Usage            | Size | Weight  | Line Height |
| ----- | ---------------- | ---- | ------- | ---------- |
| H1    | Cover main title | 64px | Black (900) | 1.1 |
| H2    | Page title       | 40px | Bold    | 1.2 |
| H3    | Section title    | 28px | Bold | 1.3 |
| H4    | Card title       | 20px | Semi-bold | 1.3 |
| P     | Body content     | 16px | Regular | 1.6 |
| High  | Highlighted data | 48px | Black | 1.1 |
| Sub   | Notes/sources    | 12px | Regular | 1.5 |
| XS    | Page number/copyright | 10px | Regular | 1.5 |

---

## V. Page Structure

### General Layout

| Area           | Position/Height | Description                            |
| -------------- | --------------- | -------------------------------------- |
| **Header Area** | y=0-80px | Minimal, often just left-aligned title |
| **Grid Content Area** | y=80, h=480px | Strict 8px grid alignment for all elements |
| **Bottom Footer** | y=590, h=130px | Clean minimal footer |

### Key Design Features

- **Strict 8px grid**: All elements align perfectly to 8px increments
- **Generous white space**: Emphasis on breathing room and negative space
- **Clean geometric lines**: Sharp corners, precise alignment
- **Single accent**: Only one accent color used sparingly for emphasis
- **No decorative clutter**: Every element serves a purpose

---

## VI. Page Types

### 1. Cover Page (01_cover.svg)

- White background
- Large left-aligned title in black
- Subtitle and author info in gray
- Thin black horizontal divider
- Accent stripe on left edge

### 2. Table of Contents Page (02_toc.svg)

- White background
- Top-left title
- Clean numbered list with strict vertical spacing
- Each item connected by vertical lines (grid precision)

### 3. Chapter Divider Page (02_chapter.svg)

- Black background
- White chapter number and title
- Accent color for chapter number background block
- Maximum contrast

### 4. Content Page (03_content.svg)

- White background
- Top-left page title
- Content in grayscale cards with sharp borders
- Strict grid layout for multiple content blocks
- Footer with section and page number

### 5. Ending Page (04_ending.svg)

- Black background
- Large "Thank You" in white centered
- Contact info in light gray below
- Accent color decorative element

---

## VII. Layout Patterns

| Pattern            | Use Cases                      |
| ------------------ | ------------------------------ |
| **Full-width image + caption** | Architectural photography, design showcase |
| **Two-column strict grid** | Side-by-side project comparison |
| **Four-square grid** | Project thumbnails, portfolio pieces |
| **Single content card** | Key concept, about the author |
| **Vertical timeline** | Project progression, career history |

---

## VIII. Spacing Guidelines (Strict 8px grid)

| Element            | Value  |
| ------------------ | ------ |
| Grid unit | 8px |
| Card gap | 32px (4 units) |
| Card padding | 32px (4 units) |
| Card border radius | 0px (sharp corners) |
| Card border | 1px solid #AAAAAA |
| Title-to-content gap | 40px (5 units) |
| Vertical rhythm baseline | 16px (2 units) |

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
| `{{SUBTITLE}}`     | Presentation subtitle / topic |
| `{{AUTHOR}}`       | Presenter name     |
| `{{DATE}}`         | Presentation date       |
| `{{ACCENT_COLOR}}` | Custom accent color (default: #000000) |
| `{{PAGE_TITLE}}`   | Page title         |
| `{{CHAPTER_NUM}}`  | Chapter number     |
| `{{CHAPTER_TITLE}}`| Chapter title      |
| `{{THANK_YOU}}`    | Thank-you message  |
| `{{CONTACT}}` | Contact information |
| `{{PAGE_NUM}}`     | Page number        |
| `{{SECTION_NAME}}` | Section name (footer) |

---

## XI. Design Checklist

### Before Generation

- [ ] Does every element align to the 8px grid?
- [ ] Is the accent color used sparingly (less than 10% of area)?
- [ ] Is there sufficient white space/negative space?
- [ ] Is the typography strictly following the weight hierarchy?

### After Generation

- [ ] viewBox = `0 0 1280 720`
- [ ] No prohibited elements
- [ ] Text has strong contrast (black on white, white on black)
- [ ] Content is within the safe area
- [ ] All coordinates are multiples of 8
- [ ] No rounded corners unless explicitly intended
