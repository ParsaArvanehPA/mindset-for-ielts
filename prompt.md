# IELTS Study Guide Generator — Master Prompt

## Mission
Create a **single-file HTML** study guide / exam preparation booklet from a Mindset for IELTS textbook chapter PDF. The output is a competition-winning, clean minimal design that summarizes every lesson, every skill, provides exam skills for each, and adds extra practice with answer keys at the end.

---

## Input
- A PDF of one chapter (unit) from **Mindset for IELTS Level 3**
- Each chapter covers **4 skills**: Reading, Writing, Listening, Speaking
- Each skill section contains: Lead-in → Core concepts/strategies → Grammar/Vocabulary focus → Exam Skills

## Output
- **One self-contained HTML file** (all CSS inline in `<style>`, all JS inline in `<script>`, no external dependencies except Google Fonts CDN)
- Language: **Full English**
- Difficulty of extra exercises: **Mixed levels** (moderate + challenging)
- Include **answer keys** with toggle show/hide
- Design: **Clean minimal** — white background, subtle colors, typography-focused premium feel

---

## Design System (EXACT specifications)

### Fonts (Google Fonts CDN)
```
Inter: weights 300, 400, 500, 600, 700, 800, 900 — body text, UI
Playfair Display: weights 400, 700, italic 400 — headings, cover title
JetBrains Mono: weights 400, 500 — code, prefix examples
```

### Color Palette
```css
--bg: #FAFAFA;                    /* page background */
--surface: #FFFFFF;               /* card background */
--text: #1a1a2e;                  /* primary text — dark navy-black */
--text-secondary: #555770;        /* body text, descriptions */
--text-muted: #8E8EA0;            /* subtle labels, metadata */
--border: #E8E8EF;                /* card borders, dividers */

/* Skill colors — each skill gets a main color, light bg, and border */
--reading: #C8962E;               /* golden amber */
--reading-light: #FFF8ED;
--reading-border: #F0DFB8;

--writing: #D4556B;               /* coral rose */
--writing-light: #FFF0F2;
--writing-border: #F5C6CE;

--listening: #8B5CF6;             /* purple violet */
--listening-light: #F5F0FF;
--listening-border: #DDD0F7;

--speaking: #0D9488;              /* teal green */
--speaking-light: #F0FDFA;
--speaking-border: #B2DFDB;

/* Functional colors */
--tip-bg: #F0F7FF;                /* tip boxes — light blue */
--tip-border: #B8D4F0;
--exam-bg: #FFF7ED;               /* exam skill boxes — warm orange */
--exam-border: #FBBF24;
--answer-bg: #F0FDF4;             /* answer sections — light green */
--answer-border: #34D399;
```

### Shadows
```css
--shadow-sm: 0 1px 2px rgba(0,0,0,0.04);
--shadow-md: 0 4px 12px rgba(0,0,0,0.06);
--shadow-lg: 0 8px 30px rgba(0,0,0,0.08);
```

### Border Radius
```css
--radius: 12px;      /* cards, exam boxes */
--radius-sm: 8px;    /* inner elements, tips, tables */
```

### Typography Scale
| Element | Font | Size | Weight | Color |
|---------|------|------|--------|-------|
| Cover title | Playfair Display | clamp(2.5rem, 6vw, 4.5rem) | 700 | --text, italic span in --reading |
| Cover subtitle | Inter | clamp(1.1rem, 2.5vw, 1.5rem) | 400 | --text-secondary |
| Section title | Playfair Display | 2rem | 700 | --text |
| Card h3 | Inter | 1.15rem | 700 | --text |
| Card h4 | Inter | 0.95rem | 700 | --text |
| Body text | Inter | 0.92rem | 400 | --text-secondary |
| Badge | Inter | 0.65rem | 700 | skill color, uppercase, letter-spacing 1px |
| Tip prefix | Inter | 0.7rem | 700 | #3B82F6, uppercase, letter-spacing 1.5px |
| Nav links | Inter | 0.8rem | 600 | --text-muted, skill color on hover/active |

### Body
```css
line-height: 1.7;
-webkit-font-smoothing: antialiased;
```

---

## Page Structure (EXACT order)

### 1. COVER PAGE
- Full viewport height (`min-height: 100vh`), centered flex column
- Background: `linear-gradient(160deg, #FAFAFA 0%, #F0F0F5 50%, #E8EAF0 100%)`
- Two decorative `::before` and `::after` pseudo-element circles (radial gradients, reading color and listening color, ~5-6% opacity, 500-600px diameter, positioned at top-right and bottom-left corners)
- Elements top-to-bottom:
  1. **Badge pill**: "Complete Exam Preparation Guide" — small caps, border, rounded 100px
  2. **Title**: `Mindset for <span>IELTS</span> 3` — the span is italic + reading color
  3. **Subtitle**: `Unit XX — [Unit Title]`
  4. **Skill pills row**: 4 pills (Reading, Writing, Listening, Speaking) each with their skill color border + light bg
  5. **Meta line**: "Study Guide • Exam Skills • Extra Practice • Answer Keys"

### 2. STICKY NAVIGATION
- `position: sticky; top: 0; z-index: 100`
- Frosted glass effect: `background: rgba(250,250,250,0.85); backdrop-filter: blur(20px)`
- Bottom border: 1px solid --border
- Horizontal scroll, hidden scrollbar
- Links: Reading, Writing, Listening, Speaking, Extra Practice, Answer Keys
- Each link has a skill-class (r/w/l/s/x) that colors the bottom-border and text on hover/active
- Active state determined by scroll position via JS IntersectionObserver-style scroll listener

### 3. MAIN CONTENT (`max-width: 860px; margin: 0 auto; padding: 0 1.5rem 4rem`)

For **each of the 4 skills** (Reading, Writing, Listening, Speaking):

#### Section Header
- `section-icon`: 48x48px rounded square, white letter on skill-colored bg
- `section-title`: Playfair Display 2rem
- `section-sub`: skill topics listed with bullet separators, muted color, left-padded to align with title

#### Content Cards (in this order):
1. **"In This Unit You Will Learn How To"** — skills-list with numbered circles in skill color
2. **Core Concept Cards** — one card per major concept, each with:
   - h3 with badge pill (skill color)
   - Explanation text
   - Tables (`.styled-table`) where applicable
   - Tip boxes (`.tip`) with 💡 TIP prefix
3. **Grammar/Vocabulary Cards** — tables, examples, word lists
4. **Exam Skills Box** (`.exam-box`) — orange-bordered, warm bg, contains the actual exam exercise from the textbook with:
   - Passage boxes (`.passage`) with colored left-border and letter labels
   - Question blocks with numbered circles
   - Fill-in blanks (`.q-blank` — dashed bottom border)
   - Radio button options where applicable

### 4. EXTRA PRACTICE SECTION
- Section icon: black bg with "+" letter
- Contains NEW exercises (not from the textbook) in cards with difficulty badges:
  - `Moderate` — same level as textbook
  - `Challenging` — slightly harder
- Exercise types:
  - **Reading**: New matching headings passage (4 paragraphs, 6 headings with 2 distractors), topic sentence identification
  - **Reading**: Prefix fill-in exercise (10 questions)
  - **Writing**: Structure transformation (verb+adverb ↔ adjective+noun, 6 questions)
  - **Writing**: Full Task 1 practice with new data set
  - **Listening**: Names & numbers written form practice (8 questions)
  - **Grammar**: Future time conditionals fill-in (6 questions) + sentence building (5 open-ended)
  - **Speaking**: Full practice set — Part 1 questions (4), Part 2 task card, Part 3 discussion (4)

### 5. ANSWER KEYS SECTION
- Section icon: green bg (#059669) with checkmark ✓
- One card per exercise group
- Each card has:
  - h3 title
  - `.answer-toggle` button (green pill, "Show Answers" / "Hide Answers")
  - `.answer-content` div (hidden by default, toggled via JS `classList.toggle('visible')`)
  - Answers in tables with explanations where helpful
  - Grid-2 layout for simple answer lists

### 6. FOOTER
- Centered, top border, unit title + "Study Guide & Exam Preparation Booklet"
- Font size 0.75–0.8rem, muted color

---

## Component Specifications

### `.card`
```css
background: var(--surface);
border: 1px solid var(--border);
border-radius: var(--radius);     /* 12px */
padding: 2rem;
margin-bottom: 1.5rem;
box-shadow: var(--shadow-sm);
```

### `.tip`
```css
background: var(--tip-bg);        /* #F0F7FF */
border: 1px solid var(--tip-border);
border-radius: var(--radius-sm);  /* 8px */
padding: 1.25rem 1.5rem;
margin: 1.5rem 0;
/* Has ::before with "💡 TIP" in blue uppercase */
```

### `.exam-box`
```css
border: 2px solid var(--exam-border);  /* #FBBF24 */
border-radius: var(--radius);
padding: 2rem;
margin: 2rem 0;
background: var(--exam-bg);            /* #FFF7ED */
/* h3 inside: uppercase, letter-spacing 1px, color #B45309 */
```

### `.passage`
```css
background: #F8F9FA;
border-left: 4px solid var(--border);
padding: 1.5rem;
border-radius: 0 8px 8px 0;
/* .label inside: 24x24 colored square with white letter */
```

### `.styled-table`
```css
/* thead: --text bg, white text, uppercase 0.78rem */
/* th first-child: top-left radius, th last-child: top-right radius */
/* td: padding 10px 16px, bottom border */
/* tr:hover td: #F8F9FA bg */
/* code inside: JetBrains Mono, #F0F0F5 bg, 4px radius */
```

### `.question`
```
- padding 1rem 0, bottom border
- .q-num: 28px circle, --text bg, white number
- .q-text: font-weight 500
- .q-options: labels with radio buttons, indented 38px
- .q-blank: inline dashed bottom-border, min-width 150px
```

### `.answer-toggle` + `.answer-content`
```
- Toggle: green pill button, 100px radius, #059669 text, answer-bg background
- Content: hidden by default, display:none → display:block via .visible class
- JS: onclick toggleAnswer(btn) — toggles .visible on nextElementSibling, updates button text
```

### `.task-card` (Speaking Part 2)
```css
background: linear-gradient(135deg, #F8F9FA 0%, #FFFFFF 100%);
border: 2px solid var(--border);
border-radius: var(--radius);
padding: 2rem;
/* h4 with bottom border, ul with disc bullets, .instruction in italic muted */
```

---

## Responsive Behavior
```css
@media (max-width: 700px) {
  .grid-2, .grid-3 { grid-template-columns: 1fr; }
  .section-sub { padding-left: 0; }
  .card { padding: 1.25rem; }
}
```

## Print Styles
```css
@media print {
  .sticky-nav { display: none; }
  .cover { min-height: auto; padding: 3rem 0; page-break-after: always; }
  .section { page-break-before: always; }
  .card { box-shadow: none; border: 1px solid #ccc; }
  .answer-content { display: block !important; }
  body { font-size: 11pt; }
}
```

---

## JavaScript (minimal)
1. **`toggleAnswer(btn)`**: Toggles `.visible` class on `btn.nextElementSibling`, flips button text between "Show Answers" and "Hide Answers"
2. **Scroll spy**: On `window.scroll`, iterate through `section[id]` elements, find which one is in view (offsetTop - 80), add `.active` class to matching nav link

---

## Content Extraction Rules
When processing a new chapter PDF:

1. **Read ALL pages** of the PDF thoroughly
2. **Identify the 4 skill sections** and their sub-topics from the "In this unit you will learn how to" boxes
3. **For each skill, extract:**
   - All conceptual explanations and strategy notes (from info boxes marked with ◎)
   - All tips (from TIP boxes)
   - All grammar rules and vocabulary lists
   - All exam skill exercises (passages, questions, task prompts)
4. **For extra practice, CREATE NEW exercises** that:
   - Follow the same format as textbook exercises
   - Are thematically related to the unit topic (e.g., urban/rural life)
   - Include moderate AND challenging difficulty
   - Cover: reading comprehension, vocabulary, writing structures, listening skills, grammar, speaking prompts
5. **For answer keys:**
   - Provide answers to ALL textbook exam skill exercises
   - Provide answers to ALL extra practice exercises
   - Include brief explanations where the answer is non-obvious

---

## Quality Checklist
- [ ] Single HTML file, no external dependencies except Google Fonts
- [ ] All 4 skills covered with full summaries
- [ ] Every concept, strategy, tip, and grammar point from the chapter included
- [ ] Exam skills exercises reproduced faithfully
- [ ] 8+ extra practice exercises created (at least 2 per skill)
- [ ] All answer keys present with toggle functionality
- [ ] Responsive on mobile
- [ ] Print-friendly
- [ ] Scroll spy navigation working
- [ ] No emojis except 💡 in tip boxes
- [ ] Formal, professional tone throughout
- [ ] Color coding consistent per skill
