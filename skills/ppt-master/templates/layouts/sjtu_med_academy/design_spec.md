# SJTU Medicine Academic Template - Design Specification

> Suitable for medical course discussion classes, academic reports, thesis defense, medical student presentations, public health topics. Based on Shanghai Jiao Tong University School of Medicine brand color.

---

## I. Template Overview

| Property       | Description                                            |
| -------------- | ------------------------------------------------------ |
| **Template Name** | sjtu_med_academy                                    |
| **Use Cases**  | Course discussion classes, academic reports, thesis defense, medical education presentations |
| **Design Tone** | Professional, clean, rigorous, academic, trustworthy |
| **Theme Mode** | Light theme (white background + deep crimson primary)   |

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

## III. Color Scheme (based on SJTU Medicine brand)

### Primary Colors

| Role           | Value       | Notes                            |
| -------------- | ----------- | -------------------------------- |
| **Primary Crimson** | `#8B0000` | SJTU brand color, used for top bar, accents, headings |
| **Secondary Navy** | `#1E3A5F` | Secondary headings, accents |
| **Gold Accent** | `#C9B037` | Highlights, decorations |
| **Background White** | `#FFFFFF` | Main page background           |

### Text Colors

| Role           | Value       | Usage                  |
| -------------- | ----------- | ---------------------- |
| **Dark Text** | `#1A1A1A`   | Primary body content           |
| **Body Text** | `#333333`   | Regular body content |
| **Muted Text** | `#666666` | Descriptions, annotations |
| **Light Gray** | `#999999`  | Footer, auxiliary info |
| **White Text** | `#FFFFFF`   | Text on colored backgrounds |

### Neutral Colors

| Role           | Value       | Usage                  |
| -------------- | ----------- | ---------------------- |
| **Card Background** | `#F5F5F5`   | Card inner background |
| **Border Gray** | `#E0E0E0`  | Borders, dividers |

### Functional Colors

| Usage      | Value       | Description    |
| ---------- | ----------- | -------------- |
| **Success** | `#2E7D32`  | Positive indicators (normal physiology, recovery) |
| **Warning** | `#D32F2F`  | Warning/abnormal/pathology |
| **Info**   | `#1E3A5F`   | Information/notes |

---

## IV. Typography System

### Font Stack

**Font Stack**: `"SF Pro Display", -apple-system, BlinkMacSystemFont, "PingFang SC", "Hiragino Sans GB", "Microsoft YaHei", "Segoe UI", sans-serif`

### Font Size Hierarchy

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
| **Top Crimson Bar** | y=0, h=60px | Full-width deep crimson bar with centered page title |
| **Content Area** | y=70, h=520px | Main content area |
| **Bottom Footer** | y=620, h=100px | Footer with institution, page number |

### Decorative Elements

- **Top crimson bar**: Consistent across all content pages
- **Left crimson accent stripe**: 6px width on left side for section dividers
- **Gold accent**: Used for key highlights and important findings

---

## VI. Page Types

### 1. Cover Page (01_cover.svg)

- White background
- Top SJTU logo placeholder area
- Large centered title + subtitle
- Bottom: course name, presenter name, date, institution

### 2. Table of Contents Page (02_toc.svg)

- White background
- Top crimson bar with "Contents" title
- Single-column list of topics, each with numbered bullet

### 3. Chapter Divider Page (02_chapter.svg)

- White background
- Large chapter number on left in crimson low opacity
- Chapter title on right with accent stripe
- Short chapter description below title

### 4. Content Page (03_content.svg)

- Top crimson bar with page title
- Full-width content area below
- Content organized in clean white cards with subtle shadows
- Footer with section name and page number

### 5. Ending Page (04_ending.svg)

- White background
- Large centered "Thank You" in crimson
- Contact information below
- Bottom institution name

---

## VII. Layout Patterns

| Pattern            | Use Cases                      |
| ------------------ | ------------------------------ |
| **Single full-width card** | Main content, key discussion |
| **Two-column content** | Side-by-side comparison, anatomy/image + text |
| **Three/four card grid** | Differential diagnosis, key points |
| **Image + text** | Clinical image + description |
| **Table** | Patient data, experimental results |

---

## VIII. Spacing Guidelines (8px grid)

| Element            | Value  |
| ------------------ | ------ |
| Card gap           | 24px   |
| Card padding       | 28px   |
| Card border radius | 12px    |
| Card shadow | soft filter (stdDev 8, opacity 0.08) |
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

Templates use `{{PLACEHOLDER}}` format placeholders:

| Placeholder        | Description        |
| ------------------ | ------------------ |
| `{{TITLE}}`        | Presentation main title |
| `{{SUBTITLE}}`     | Presentation subtitle / topic |
| `{{COURSE}}`       | Course name |
| `{{AUTHOR}}`       | Presenter name     |
| `{{INSTRUCTOR}}` | Instructor       |
| `{{INSTITUTION}}`  | Shanghai Jiao Tong University School of Medicine |
| `{{DATE}}`         | Presentation date       |
| `{{PAGE_TITLE}}`   | Page title         |
| `{{CHAPTER_NUM}}`  | Chapter number     |
| `{{CHAPTER_TITLE}}`| Chapter title      |
| `{{THANK_YOU}}`    | Thank-you message  |
| `{{CONTACT}}` | Contact information |
| `{{PAGE_NUM}}`     | Page number        |
| `{{SECTION_NAME}}` | Section name (footer) |

---

## XI. Component Specifications

### Content Card with Shadow

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
<rect x="80" y="140" width="1040" height="360" rx="12" fill="#FFFFFF" filter="url(#softShadow)" stroke="#E0E0E0" stroke-width="1"/>
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
- [ ] Does the color scheme follow the specification (crimson primary)
- [ ] Is the font size hierarchy correct

### After Generation

- [ ] viewBox = `0 0 1280 720`
- [ ] No prohibited elements
- [ ] Text is readable (≥12px)
- [ ] Content is within the safe area
- [ ] Elements are properly aligned to 8px grid
- [ ] Style consistency check passed
