# Workflow: Adding a New Session to the Site

Run this after each class to add the session content to the curriculum site.

---

## Inputs

Drop these into `lesson-N/`:
1. **Video recording** — the full session MP4 (e.g., `AI Jam Mar 31 2026.mp4`)
2. **Transcript** — Granola export with timestamps (e.g., `lesson N transcript.md`)
3. **Any co-instructor materials** — slide decks, HTML files, etc.

---

## Steps

### 1. Write the lesson content
From the transcript, create two files in `lesson-N/`:
- **`lesson N.md`** — Written walkthrough distilled from the transcript. Include:
  - What was covered (section-by-section summary)
  - Key concepts and terms (table format)
  - Key takeaways (numbered list)
  - What's next (preview of the following session)
- **`homework N.md`** — Homework assignment for the next session

### 2. Build `session-N.html`
Clone the previous session's HTML page as a template. Update:
- **Hero:** Session number, title, date, duration, participant count, guest instructor (if any)
- **Skills Learned:** Bullet list of what was covered (with checkmarks)
- **TL;DR grid:** Homework preview + key links/resources
- **Video section:** Embed the full recording (local MP4 or Fathom embed)
- **Written Walkthrough:** Collapsible `<details>` sections for each concept/step
- **Homework card:** Setup checklist, practice tasks, what's coming next

### 3. Update `index.html`
- Flip current session from "Up Next" → "Completed" (change class to `status-completed`, add `clickable` class, wrap in `<a>` tag linking to session page, add arrow element)
- Flip next session from "Coming Soon" → "Up Next" (change class to `status-upnext`, add SVG dot badge)
- **Add new cheat sheet group** for commands/terms introduced in this session (under the "What We've Learned So Far" section)

### 4. Extract video highlight clips
Identify 5-6 key moments from the transcript (demos, concept explanations, aha moments). Use ffmpeg:
```bash
ffmpeg -i "lesson-N/VIDEO.mp4" -ss HH:MM:SS -to HH:MM:SS \
  -c:v libx264 -preset fast -crf 23 -c:a aac -b:a 128k \
  "assets/videos/session-N/CLIP_NAME.mp4" -y
```

Generate thumbnails from the middle of each clip:
```bash
ffmpeg -i "assets/videos/session-N/CLIP.mp4" -ss 00:00:05 \
  -vframes 1 -q:v 2 "assets/thumbnails/session-N/CLIP.jpg" -y
```

### 5. Update CONTEXT.md
- Update the curriculum arc with the new session status
- Update "Current Status" line

### 6. Deploy
- Commit changes
- Push to GitHub
- Vercel auto-deploys from main

---

## File structure per session

```
lesson-N/
├── AI Jam [DATE].mp4          # Full recording
├── lesson N transcript.md     # Granola transcript
├── lesson N.md                # Written walkthrough
├── homework N.md              # Homework
└── [co-instructor files]      # Slides, etc.

assets/videos/session-N/       # Highlight clips
assets/thumbnails/session-N/   # Clip thumbnails

session-N.html                 # Session page (at project root)
```

---

## Checklist

- [ ] `lesson-N/lesson N.md` written
- [ ] `lesson-N/homework N.md` written
- [ ] `session-N.html` created (cloned from previous session template)
- [ ] `index.html` updated (session status + cheat sheet)
- [ ] Video clips extracted to `assets/videos/session-N/`
- [ ] Thumbnails generated to `assets/thumbnails/session-N/`
- [ ] `CONTEXT.md` updated
- [ ] Committed and pushed
