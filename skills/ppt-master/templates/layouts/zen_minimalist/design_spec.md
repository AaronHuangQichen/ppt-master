# Zen Minimalist Template - Design Specification

> Suitable for academic lectures, wellness presentations, personal brand talks, keynote speeches, mindfulness topics. Characterized by extreme white space, low contrast, natural muted tones, and a calm, serene feeling.

---

## I. Template Overview

| Property       | Description                                            |
| -------------- | ------------------------------------------------------ |
| **Template Name** | zen_minimalist                                    |
| **Use Cases**  | Academic lectures, wellness/health topics, personal branding, keynote speeches, mindfulness, serene/quiet topics |
| **Design Tone** | Calm, serene, minimalist, spacious, tranquil, sophisticated |
| **Theme Mode** | Light theme with massive negative space, muted natural accent colors |

---

## II. Canvas Specification

| Property       | Value                         |
| -------------- | ----------------------------- |
| **Format**     | Standard 16:9                 |
| **Dimensions** | 1280 × 720 px                |
| **viewBox**    | `0 0 1280 720`                |
| **Page Margins** | Left/Right 96px, Top/Bottom 80px (extra wide margins for more breathing room) |
| **Safe Area**  | x: 96-1184, y: 80-640        |

---

## III. Color Scheme (Muted Natural Palette)

### Primary Muted Colors

| Role           | Value       | Notes                            |
| -------------- | ----------- | -------------------------------- |
| **Muted Sage** | `#6b9080` | Primary accent, natural calm green |
| **Warm Gray**  | `#4a4a48` | Primary text |
| **Cool Gray**  | `#6c757d` | Body text |
| **Light Gray** | `#adb5bd` | Borders, dividers |
| **Ultra Pale** | `#f8f9fa` | Card backgrounds |
| **Cream White**| `#ffffff` | Main page background (off-white for softer contrast) |

The template allows for custom muted accent colors (soft green, dusty blue, muted rose) depending on topic.

### Text Colors (Low Contrast)

| Role           | Value       | Usage                  |
| -------------- | ----------- | ---------------------- |
| **Dark Gray** | `#4a4a48`   | Headings |
| **Body Gray** | `#6c757d`   | Regular body content |
| **Muted Gray** | `#868e96` | Descriptions, annotations |
| **Pale Gray** | `#adb5bd`  | Footer, auxiliary info |
| **White** | `#FFFFFF`   | Text on colored backgrounds |

---

## IV. Typography System

### Font Stack

**Font Stack**: `"SF Pro Display\", -apple-system, BlinkMacSystemFont, \"PingFang SC\", \"Hiragino Sans GB\", \"Microsoft YaHei\", \"Segoe UI\", sans-serif`

### Font Size Hierarchy (Airy Spacing)

| Level | Usage            | Size | Weight  | Line Height |
| ----- | ---------------- | ---- | ------- | ---------- |
| H1    | Cover main title | 52px | Light | 1.3 |
| H2    | Page title       | 36px | Regular | 1.4 |
| H3    | Section title    | 24px | Medium | 1.4 |
| H4    | Card title       | 20px | Medium | 1.4 |
| P     | Body content     | 16px | Light | 1.8 |
| High  | Highlighted data | 36px | Regular | 1.2 |
| Sub   | Notes/sources    | 12px | Light | 1.6 |
| XS    | Page number/copyright | 10px | Light | 1.5 |

---

## V. Page Structure

### General Layout

| Area           | Position/Height | Description                            |
| -------------- | --------------- | -------------------------------------- |
| **Massive Whitespace** | Everywhere | 50%+ of page should be empty |
| **Content Centered** | Horizontal center | Content is typically centered for balance |
| **Minimal Footer** | Very bottom | Subtle page number |

### Key Design Features

- **Extreme white space**: Less content = more impact, maximum 3-5 points per page
- **Low contrast**: Softer on eyes, calm reading experience
- **Rounded corners**: Gentle 16px rounded corners on all cards
- **Soft shadows**: Very subtle shadows for gentle depth
- **Centered composition**: Balanced, symmetrical arrangement

---

## VI. Page Types

### 1. Cover Page (01_cover.svg)

- Cream background
- Extremely spaced out
- Centered title (light weight)
- Subtitle far below title
- Author/date at bottom with massive space above

### 2. Table of Contents Page (02_toc.svg)

- Cream background
- Centered "Contents" title at top
- Vertically spaced list of topics, centered alignment
- Large spacing between items

### 3. Chapter Divider Page (02_chapter.svg)

- Muted accent background
- Centered chapter number (low opacity)
- Centered chapter title in white
- Massive whitespace all around

### 4. Content Page (03_content.svg)

- Cream background
- Centered page title at top
- One or two gentle cards with large spacing
- No clutter, only essential content

### 5. Ending Page (04_ending.svg)

- Cream background
- Large centered "Thank You"
- Contact info with generous spacing
- Extreme bottom spacing

---

## VII. Layout Patterns

| Pattern            | Use Cases                      |
| ------------------ | ------------------------------ |
| **Single centered idea** | Key takeaway, quote, main concept |
| **Two spaced cards** | Two concepts with balanced space |
| **Quote full width** | Featured quote with large margins |
| **Image + minimal caption** | One large image with caption below |

---

## VIII. Spacing Guidelines (Extra Airy)

| Element            | Value  |
| ------------------ | ------ |
| Page margins | 96px left/right, 80px top/bottom |
| Card gap | 48px extra spacing |
| Card padding | 40px generous padding |
| Card border radius | 16px gentle rounded corners |
| Card shadow | very soft (stdDev 6, opacity 0.05) |
| Title-to-content gap | 64px massive gap |
| Line height body | 1.8 for airy reading |

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
| `{{ACCENT_COLOR}}` | Custom muted accent (default: #6b9080) |
| `{{PAGE_TITLE}}`   | Page title         |
| `{{CHAPTER_NUM}}`  | Chapter number     |
| `{{CHAPTER_TITLE}}`| Chapter title      |
| `{{THANK_YOU}}`    | Thank-you message  |
| `{{CONTACT}}` | Contact information |
| `{{PAGE_NUM}}`     | Page number        |

---

## XI. Design Checklist

### Before Generation

- [ ] Is content extremely sparse (max 3 bullet points)?
- [ ] Is there more than 40% white space?
- [ ] Is contrast soft, not harsh?
- [ ] Are all corners rounded with 16px radius?

### After Generation

- [ ] viewBox = `0 0 1280 720`
- [ ] No prohibited elements
- [ ] Text is still readable despite low contrast (≥ 16px size)
- [ ] Content is within the expanded safe area
- [ ] Spacing is generous and calm
- [ ] Everything is gently centered and balanced
