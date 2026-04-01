# AI Native — Project Plan

> A website to host the AI Builders curriculum for Change.org's design and product team. Built by Maroun Najjar, Senior Director of Design.

---

## What This Is

A single-page (or multi-page) website that serves two purposes:
1. **Curriculum overview** — the full arc of sessions, what each covers, and what's coming next.
2. **Session recaps** — for each completed session, a detailed written walkthrough + homework + video highlights so anyone can follow along at home.

The site is internal-facing. Audience is the design and product team at Change.org.

---

## Design Direction

**Match the aesthetic of the Supporter Experience Design Sprint Recap site** (`projects/design-sprint-reel/sprint-recap.html`). Specifically:

### Color Tokens
```css
--bg: #0f1117;
--surface: #1a1d27;
--surface2: #232733;
--border: #2e3340;
--text: #e4e6eb;
--text-muted: #8b8fa3;
--accent: #6c5ce7;
--accent2: #a29bfe;
--green: #00b894;
--orange: #fdcb6e;
--pink: #fd79a8;
--blue: #74b9ff;
--red: #ff6b6b;
--teal: #81ecec;
```

### Typography & Layout
- Font: `-apple-system, BlinkMacSystemFont, 'SF Pro Display', 'Segoe UI', system-ui, sans-serif`
- Max-width container: `960px`
- Dark background, light text, purple gradient accents
- Section labels: 11px uppercase, letter-spacing 2px, accent color pill badges
- Gradient hero text: `linear-gradient(135deg, var(--text) 0%, var(--accent2) 100%)` with `-webkit-background-clip: text`
- Cards: `var(--surface)` background, `var(--border)` borders, `16px` border-radius
- Hover states on interactive cards (border-color transitions to accent)
- Collapsible `<details>` elements for long-form content
- Responsive: single-column on mobile

### Motion
- Use Framer Motion for tasteful hover effects, scroll animations, and transitions
- Keep motion native-feeling — no flashy or cheap effects
- Subtle scale + translate on hover for people/card elements
- Fade-in on scroll for sections

### Key Patterns from Sprint Recap to Reuse
- **Hero section**: gradient background, pill label, large gradient title, subtitle, meta row
- **Highlight reel video**: full-width video player below hero
- **Section structure**: section-label (uppercase pill) → h2 → content
- **Card grids**: surface-colored cards with left-colored borders for categorization
- **Collapsible details**: for long-form written content (expandable sections)
- **Team chips**: avatar + name pills
- **Person cards**: circular avatar, hover scale effect, colored border on hover
- **Video embeds**: rounded corners, dark background, inline within cards

---

## Site Structure

### Landing Page (index.html)

**Hero**
- Title: "AI Native"
- Subtitle: "Teaching Change.org's design and product team to build with AI."
- Meta: "Led by Maroun Najjar · 5 Sessions · March–April 2026"

**Curriculum Overview Section**
A visual timeline or card grid showing all 5 sessions. Each card shows:
- Session number + title
- One-line description of what you walk away with
- Status badge: `Completed` (green), `Up Next` (accent/purple), `Coming Soon` (muted)
- For completed sessions: link to the full session page

| # | Title | Status | Description |
|---|-------|--------|-------------|
| 1 | **Setup + First Build** | Completed | Install Claude Code, create your first website, learn 3 iteration methods |
| 2 | **Ship It: GitHub + Deploy** | Up Next | Version control, deploy to a live URL, share your work internally |
| 3 | **Claude Code ↔ Canvas** | Coming Soon | Bridge code and visual canvas, agents spinning up design variations |
| 4 | **Mission Control** | Coming Soon | Manage multiple Claude Code instances, parallel builds, organized workflow |
| 5 | **Cowork + Agents** | Coming Soon | Claude as your daily ops assistant, agents on schedules and triggers |

**Participants Section**
Grid of participant avatars/names (similar to the sprint recap's people grid):
- Maroun Najjar (facilitator)
- Lizzie Belgum
- Corinne Sherry
- Janice Pang
- Jen Garfield
- Justin Greenstein
- Katelyn Burgin
- Lia Siebert
- Hamish Chandra
- Rowan Rosenthal
- Samara Tager

**Links & Resources Section**
Key tools referenced across the curriculum:
- Claude Code install command
- Visual Explainer skill (GitHub)
- Compound Engineering skill (GitHub)
- Agentation
- Framer Motion
- Handy Computer
- Agent Browser

---

### Session Pages (e.g., session-1.html)

Each completed session gets its own page with this structure:

**Hero**
- Session number pill label
- Title (e.g., "Setup + First Build")
- Date, duration, participant count
- Back link to curriculum overview

**TL;DR Section** (for people who attended)
- Quick summary: 3-5 bullet points of what was covered
- Homework assignment (the short Slack-style version)
- Key links used in this session

**Full Video**
- The full session recording (mp4) embedded at the top, similar to the sprint recap's highlight reel placement
- Caption: "Watch the full session, or scroll down for the written walkthrough."

**Highlight Clips** (extracted from the video)
- Short video clips of key moments, embedded inline within the walkthrough content
- Similar to how the sprint recap embeds individual solution videos within cards
- For Session 1, pull clips of:
  - Maroun's intro / lay of the land (~0:42–3:00)
  - The terminal walkthrough / folder setup
  - First Claude Code summon
  - First website generation reveal
  - Iteration / feedback loop demo
  - Reactions / "aha" moments from participants

**Written Walkthrough** (the full self-guided version)
- Use collapsible `<details>` sections for each step (matching sprint recap pattern)
- Content source: `lesson-1/lesson 1.md` — this is already written as a step-by-step guide
- Steps for Session 1:
  1. Create your home base folder
  2. Open Terminal and navigate
  3. Install Claude Code
  4. Summon Claude Code
  5. Install your skills (Visual Explainer, Compound Engineering)
  6. Install Agentation
  7. Find your content and build your first site
  8. Preview your site
  9. Iterate on it (3 methods)
  10. Add motion
  - Golden rule: screenshot everything

**Homework Section**
- Full homework assignment (from `lesson-1/homework 1.md`)
- Styled as a distinct card/section with clear action items

---

## Video Processing Pipeline

Follow the same workflow used for the design sprint recap (`projects/design-sprint-reel/`):

### Step 1: Transcribe
- Source video: `lesson-1/AI Jam Mar 16 2026.mp4` (466MB, ~61 min)
- Transcript already exists: `lesson-1/lesson 1 transcript.md` (Granola export with timestamps)
- Use timestamps from transcript to identify highlight moments

### Step 2: Identify Highlight Moments
Review the transcript and pull clips for key teaching moments, demo reveals, and participant reactions. Use ffmpeg to extract clips (same approach as `design-sprint-reel/scripts/build_all_clips.py`).

Suggested clips for Session 1 (refine after reviewing video):
- `01_intro_welcome.mp4` — Maroun's opening, setting expectations (~0:42–2:00)
- `02_terminal_walkthrough.mp4` — ls, cd, the three commands you need
- `03_claude_code_setup.mp4` — First summon, login, trust folder
- `04_skills_install.mp4` — Installing Visual Explainer + Compound Engineering
- `05_first_website.mp4` — The moment the first site generates
- `06_iteration_demo.mp4` — Showing the 3 feedback methods
- `07_agentation_demo.mp4` — Figma-style comments on live site
- `08_reactions.mp4` — Team reactions, aha moments

### Step 3: Generate Thumbnails
Extract a thumbnail frame from each clip (same as sprint recap's `thumbnails/` folder).

### Step 4: Embed in Page
Place clips inline within the walkthrough sections, matching the sprint recap's pattern of video within cards.

---

## File Structure

```
projects/ai-curriculum/
├── index.html                    # Landing page with curriculum overview
├── session-1.html                # Session 1 full page
├── assets/
│   ├── videos/
│   │   ├── session-1-full.mp4    # Full recording (or link to Fathom)
│   │   ├── 01_intro_welcome.mp4  # Highlight clips
│   │   ├── 02_terminal_walkthrough.mp4
│   │   └── ...
│   ├── thumbnails/               # Video thumbnail images
│   ├── profile-pictures/         # Participant photos
│   └── img/                      # Any other images/icons
├── scripts/
│   ├── extract_clips.py          # ffmpeg clip extraction (timestamps → clips)
│   └── generate_thumbnails.py    # Generate thumbnail frames from clips
├── lesson-1/                     # Source content (already exists)
│   ├── lesson 1.md               # Written walkthrough
│   ├── homework 1.md             # Homework
│   ├── lesson 1 transcript.md   # Full transcript with timestamps
│   └── AI Jam Mar 16 2026.mp4   # Full video recording
├── lesson-2/                     # Future — add as sessions happen
├── PROJECT-PLAN.md               # This file
└── README.md                     # One-liner: what this is
```

---

## Build Instructions for Claude Code

### Phase 1: Scaffold + Landing Page
1. Create the file structure above (minus video processing)
2. Build `index.html` with the full design system from the sprint recap
3. Include the curriculum overview cards, participant grid, and resources section
4. Add Framer Motion via CDN and wire up scroll animations + hover effects
5. Make it responsive

### Phase 2: Session 1 Page
1. Build `session-1.html` using the lesson content from `lesson-1/lesson 1.md` and `lesson-1/homework 1.md`
2. Structure with TL;DR at top, video embed, then collapsible walkthrough sections
3. Embed the full video at the top (reference: `lesson-1/AI Jam Mar 16 2026.mp4`)
4. Style homework section as a distinct, prominent card

### Phase 3: Video Processing
1. Write `scripts/extract_clips.py` — takes timestamp pairs and extracts clips via ffmpeg
2. Review transcript, define timestamp ranges for highlight moments
3. Extract clips and thumbnails
4. Embed clips inline in the session page walkthrough sections

### Phase 4: Polish
1. Add transitions between pages (landing → session page)
2. Ensure all motion feels tasteful and native
3. Test on mobile
4. Cross-link: session cards on landing page link to session pages, session pages link back

---

## Future Sessions

As each session happens:
1. Create a `lesson-N/` folder with the recap, homework, transcript, and video
2. Build `session-N.html` following the same template as session-1
3. Update `index.html` to flip the session status from "Up Next" → "Completed"
4. Run the video processing pipeline on the new recording
5. Post the link in #tmp-ai-builders-curriculum

---

## Reference Files

| File | What it is |
|------|-----------|
| `projects/design-sprint-reel/sprint-recap.html` | Aesthetic reference — match this look and feel |
| `projects/design-sprint-reel/scripts/build_all_clips.py` | Reference for video clip extraction pipeline |
| `projects/ai-curriculum/lesson-1/lesson 1.md` | Session 1 written walkthrough content |
| `projects/ai-curriculum/lesson-1/homework 1.md` | Session 1 homework content |
| `projects/ai-curriculum/lesson-1/lesson 1 transcript.md` | Session 1 full transcript with timestamps |
| `projects/ai-curriculum/lesson-1/AI Jam Mar 16 2026.mp4` | Session 1 full video (466MB, 61 min) |
