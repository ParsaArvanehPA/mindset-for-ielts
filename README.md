# Mindset for IELTS Level 3 — Complete Study Guide Collection

A comprehensive, interactive web-based study guide for **Mindset for IELTS Level 3**, covering all 8 units and all 4 IELTS skills (Reading, Writing, Listening, Speaking). Built as a set of self-contained HTML files and deployed on GitHub Pages.

**Live Site:** [https://parsaarvanehpa.github.io/mindset-for-ielts/](https://parsaarvanehpa.github.io/mindset-for-ielts/)

---

## What This Project Is

This project transforms the entire **Mindset for IELTS Level 3** textbook into a rich, interactive, web-based study platform. Each of the 8 units has been converted from PDF into a fully self-contained HTML study guide, and a premium gateway landing page ties them all together.

The study guides are designed to be used for exam preparation — they cover every skill focus, vocabulary section, grammar point, exam strategy, and practice exercise from the original material, restructured into an engaging, collapsible, and visually organised format.

### Who It's For

- IELTS candidates preparing for Band 7+ (advanced level)
- English language teachers looking for structured digital materials
- Self-study learners who want an organised, mobile-friendly revision tool

---

## Project Structure

```
mindset-for-ielts/
├── index.html                  # Gateway landing page (dashboard)
├── study-guide.html            # Unit 01 — Urban & Rural Life
├── unit2-study-guide.html      # Unit 02 — Health & Medicine
├── unit3-study-guide.html      # Unit 03 — Art & Architecture
├── unit4-study-guide.html      # Unit 04 — Finance & Business
├── unit5-study-guide.html      # Unit 05 — History
├── unit6-study-guide.html      # Unit 06 — Science & Technology
├── unit7-study-guide.html      # Unit 07 — TV, News & Current Affairs
├── unit8-study-guide.html      # Unit 08 — Culture
├── .github/
│   └── workflows/
│       └── deploy.yml          # GitHub Pages deployment workflow
└── README.md
```

**Total:** ~23,000 lines of hand-crafted HTML/CSS/JS across 9 files.

---

## The 8 Units

| Unit | Topic | Key IELTS Focus Areas |
|------|-------|-----------------------|
| 01 | **Urban & Rural Life** | Matching headings, Task 1 trend descriptions, form completion, Speaking Parts 1–3 |
| 02 | **Health & Medicine** | T/F/NG, Task 2 essays, multiple choice listening, health vocabulary |
| 03 | **Art & Architecture** | Summary completion, describing processes, map labelling, creative expression |
| 04 | **Finance & Business** | Paragraph matching, Task 1 charts & graphs, note completion, business vocabulary |
| 05 | **History** | Matching headings, Task 2 discussion essays, sentence completion, past tense narratives |
| 06 | **Science & Technology** | Multiple choice, Task 1 line graphs, matching features, tech vocabulary |
| 07 | **TV, News & Current Affairs** | Short answer questions, opinion essays, listening for detail, media vocabulary |
| 08 | **Culture** | Mixed question types, Task 1 & 2 review, Part 2 cue cards, cultural vocabulary |

---

## What Each Study Guide Contains

Every unit study guide follows a consistent, comprehensive structure:

### 1. Cover Page
Full-viewport dark gradient hero with unit number, topic title, and animated background effects.

### 2. Reading Section
- **Lead-In** — Warm-up vocabulary and topic introduction exercises
- **Skill Focus** — Detailed strategy breakdowns for specific question types (e.g., Matching Headings, T/F/NG, Summary Completion)
- **Vocabulary Focus** — Word formation, prefixes, suffixes, collocations, and academic vocabulary
- **Exam Skills** — Step-by-step walkthroughs of real exam-style questions
- **Extra Practice** — Additional exercises with collapsible answer keys

### 3. Writing Section
- **Lead-In** — Analysing model answers, grammar for writing
- **Skill Focus** — Task Achievement, Coherence & Cohesion, Lexical Resource, Grammatical Range
- **Language Focus** — Describing trends, comparison structures, hedging language
- **Exam Skills** — Full Task 1 and/or Task 2 practice with model answers
- **Extra Practice** — Timed writing prompts and self-assessment rubrics

### 4. Listening Section
- **Lead-In** — Synonym recognition, prediction strategies
- **Skill Focus** — Form completion, multiple choice, matching, map labelling, note completion
- **Grammar Focus** — Conditionals, relative clauses, reported speech (unit-specific)
- **Exam Skills** — Full section practice with answer breakdowns
- **Extra Practice** — Additional exercises with strategies

### 5. Speaking Section
- **Lead-In** — IELTS Speaking test format and assessment criteria
- **Part 1** — Common questions with model answers and fluency tips
- **Part 2** — Cue card practice with planning strategies and sample long turns
- **Part 3** — Discussion questions with advanced structures and opinion phrases
- **Extra Practice** — Self-recording prompts and vocabulary application

### 6. Comprehensive Review
- **Master Vocabulary List** — All key terms from the unit with definitions
- **Cross-Skill Challenge** — Exercises that combine multiple skill areas
- **Self-Assessment Checklist** — Unit learning objectives with checkboxes

### Interactive Features
- Collapsible/expandable sections using `<details>` elements
- Colour-coded skill identification (amber for Reading, rose for Writing, purple for Listening, cyan for Speaking)
- Sticky navigation within each study guide
- Smooth scroll anchors to each section
- Responsive design for mobile, tablet, and desktop
- Print-friendly styles

---

## Gateway Landing Page (`index.html`)

The landing page is a premium, app-like dashboard that serves as the main entry point to all 8 units.

### Sections

1. **Hero** — Full-viewport dark gradient with CSS-animated floating orbs, particle effects, gradient-shifting title, stats bar (8 Units, 4 Skills, 200+ Exercises, Exam Ready), and smooth-scroll CTA

2. **Skills Overview** — 4 interactive cards for Reading, Writing, Listening, and Speaking, each with its signature colour, SVG icon, and description of what's covered across all units

3. **Units Grid** — 8 large interactive cards in a 2-column layout, each featuring:
   - Unit number with gradient accent
   - Topic title and description
   - 4 skill badges (R/W/L/S)
   - Key topic tags
   - Direct link to the study guide
   - Hover effects: lift, scale, coloured shadow

4. **Learning Path** — Horizontal timeline showing the Unit 1 → 8 progression with clickable nodes linked to each study guide

5. **What You'll Master** — 4-column grid of 24 exam skill items organised by skill colour (6 per skill: Reading, Writing, Listening, Speaking)

6. **Footer** — Course branding and quick links to all 8 units

---

## Design System

All files share a unified design system:

### Typography
- **Playfair Display** — Headings and titles (serif, elegant)
- **Inter** — Body text and UI elements (sans-serif, clean)
- **JetBrains Mono** — Unit numbers, statistics, code-like elements (monospace)

### Colour Palette

| Skill | Primary | Light BG | Dark | Gradient |
|-------|---------|----------|------|----------|
| Reading | `#D97706` (amber) | `#FFFBEB` | `#92400E` | `#F59E0B → #D97706` |
| Writing | `#E11D48` (rose) | `#FFF1F2` | `#9F1239` | `#FB7185 → #E11D48` |
| Listening | `#7C3AED` (purple) | `#F5F3FF` | `#5B21B6` | `#A78BFA → #7C3AED` |
| Speaking | `#0891B2` (cyan) | `#ECFEFF` | `#155E75` | `#22D3EE → #0891B2` |

### UI Foundation
- Background: `#F8F9FC` (light pages), `#0F172A → #1E293B → #334155` (dark heroes)
- Surface: `#FFFFFF` with `1px solid #E5E7EB` borders
- Border radius: `16px` (cards), `10px` (small), `6px` (extra small)
- Shadows: 5-tier elevation system from `xs` to `2xl`

### Animations
- All animations are **CSS-only** (no external libraries)
- Scroll-reveal with `IntersectionObserver`
- Floating orbs with `blur()` filters
- Particle drift effects
- Gradient text colour shifting
- Hover transforms: lift, scale, glow, parallax

---

## Technical Details

### Architecture
- **Zero dependencies** — No frameworks, no build tools, no npm packages
- **Self-contained** — Each HTML file includes all CSS in `<style>` and all JS in `<script>`
- **Static** — Pure HTML/CSS/JS, no server required
- **Portable** — Files can be opened directly in any browser from the file system

### Fonts
Loaded from Google Fonts CDN:
```
Inter (300–900), Playfair Display (400, 700, italic), JetBrains Mono (400, 500)
```

### Browser Support
- All modern browsers (Chrome, Firefox, Safari, Edge)
- CSS Grid, Flexbox, `clamp()`, `backdrop-filter`, CSS custom properties
- `IntersectionObserver` API for scroll animations
- Responsive: mobile (< 480px), tablet (< 768px), desktop (< 1024px), wide (1280px max)

### Deployment
- **Hosting:** GitHub Pages
- **CI/CD:** GitHub Actions workflow (`.github/workflows/deploy.yml`)
- **Trigger:** Automatic deployment on every push to `main`
- **URL:** [https://parsaarvanehpa.github.io/mindset-for-ielts/](https://parsaarvanehpa.github.io/mindset-for-ielts/)

---

## How It Was Built

1. **Source Material** — The Mindset for IELTS Level 3 textbook PDFs (8 units) were used as the content source
2. **Content Extraction** — Each unit's PDF was read and all exercises, vocabulary, strategies, grammar points, and exam skills were extracted
3. **HTML Conversion** — Content was structured into semantic, accessible HTML with collapsible sections, skill-coded colours, and interactive elements
4. **Design System** — A shared CSS variable system was established for consistent typography, colours, spacing, and animations across all files
5. **Gateway Page** — A premium landing page was designed and built as the central hub linking to all 8 unit study guides
6. **Deployment** — The project was pushed to GitHub and deployed to GitHub Pages with an automated CI/CD workflow

---

## Running Locally

No build step required. Simply:

```bash
# Clone the repository
git clone https://github.com/ParsaArvanehPA/mindset-for-ielts.git

# Open in browser
open mindset-for-ielts/index.html
```

Or serve with any static file server:

```bash
cd mindset-for-ielts
python3 -m http.server 8000
# Visit http://localhost:8000
```

---

## File Sizes

| File | Lines | Description |
|------|-------|-------------|
| `index.html` | 1,448 | Gateway landing page |
| `study-guide.html` | 2,771 | Unit 01 — Urban & Rural Life |
| `unit2-study-guide.html` | 3,032 | Unit 02 — Health & Medicine |
| `unit3-study-guide.html` | 2,526 | Unit 03 — Art & Architecture |
| `unit4-study-guide.html` | 2,374 | Unit 04 — Finance & Business |
| `unit5-study-guide.html` | 3,107 | Unit 05 — History |
| `unit6-study-guide.html` | 2,898 | Unit 06 — Science & Technology |
| `unit7-study-guide.html` | 2,690 | Unit 07 — TV, News & Current Affairs |
| `unit8-study-guide.html` | 2,496 | Unit 08 — Culture |
| **Total** | **23,342** | |

---

## License

This project is an educational study aid based on *Mindset for IELTS Level 3* by Cambridge University Press. The study guides are intended for personal, non-commercial educational use only.
