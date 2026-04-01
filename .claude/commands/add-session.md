# Add Session to AI Curriculum Site

You are adding a new completed session to the AI Native curriculum site. The user has dropped source files into a `lesson-N/` folder.

## Pre-flight

1. **Detect the session number.** Look at what `lesson-N/` folders exist and which session is currently marked "Up Next" in `index.html`. Confirm with the user if ambiguous.
2. **Inventory the source files** in `lesson-N/`. You need at minimum:
   - A video recording (MP4)
   - A transcript (markdown with timestamps)
   - Optionally: co-instructor materials (slides, HTML files, etc.)
3. **Read the previous session page** (e.g., `session-{N-1}.html`) — this is your template.

## Step 1: Write lesson content

From the transcript, create two files in `lesson-N/`:

**`lesson N.md`** — Written walkthrough:
- What was covered (section-by-section, distilled from transcript)
- Key concepts and terms (table format)
- Key takeaways (numbered)
- What's next (preview of following session)

**`homework N.md`** — Homework for next session:
- Setup/prerequisite checklist
- Practice exercises
- What's coming next

## Step 2: Build session page

Clone the previous session's HTML as a template. Update:
- **Hero:** Session number, title, date, duration, participant count, guest instructor
- **Skills Learned:** Checkmark list of what was covered
- **TL;DR grid:** Homework summary + key links/resources
- **Video section:** Fathom link (ask user for URL) or local MP4 embed
- **Written Walkthrough:** Collapsible `<details>` for each concept/step from the lesson content
- **Homework card:** Checklist, practice tasks, what's coming next

Match the exact CSS and structure of the previous session page — no design changes.

## Step 3: Extract highlight clips

Identify 5-6 key moments from the transcript (demos, concept explanations, reactions). Extract via ffmpeg:

```bash
ffmpeg -i "lesson-N/VIDEO.mp4" -ss HH:MM:SS -to HH:MM:SS \
  -c:v libx264 -preset fast -crf 23 -c:a aac -b:a 128k \
  "assets/videos/session-N/CLIP_NAME.mp4" -y
```

Run all clips in background (`run_in_background: true`) for parallelism.

Generate thumbnails:
```bash
ffmpeg -i "assets/videos/session-N/CLIP.mp4" -ss 00:00:05 \
  -vframes 1 -q:v 2 "assets/thumbnails/session-N/CLIP.jpg" -y
```

Add a **Highlights** section to the session page (between Full Video and Walkthrough) with collapsible clips — use colored step-num badges:
- Pink for demos
- Blue for lesson content
- Green for wrap-up/meta

## Step 4: Update index.html

- Flip current session card from "Up Next" → "Completed" (green badge, `clickable` class, wrap in `<a>` tag, add arrow)
- Flip next session from "Coming Soon" → "Up Next" (purple badge with SVG dot)
- **Add a new cheat sheet group** under "What We've Learned So Far" with commands and terms introduced in this session. Follow the existing pattern — terminal commands get `cheat-terminal` class, concepts get plain `cheat-item`, key insights get `cheat-highlight`.

## Step 5: Update docs

- Update `CONTEXT.md` — session statuses and curriculum arc
- Update session description in `index.html` to reflect what actually happened (not what was planned)

## Step 6: Deploy

```bash
# Commit
git add .gitignore .vercelignore index.html session-N.html CONTEXT.md \
  "lesson-N/lesson N.md" "lesson-N/homework N.md" \
  [any other new lesson-N files except *.mp4]
git commit -m "Add Session N: [Title]"
git push origin main

# Deploy to Vercel
npx vercel --prod --scope change-org-team

# CRITICAL: Manually alias to production URL (auto-alias is broken)
npx vercel alias set <deployment-url-from-above> building-with-ai-syllabus.vercel.app --scope change-org-team
```

**Important deploy notes:**
- `.gitignore` excludes `lesson-N/*.mp4` and `assets/` — video files stay local only
- The `vercel alias set` step is required — without it, the production URL won't update
- Verify at https://building-with-ai-syllabus.vercel.app after aliasing

## Checklist

Before finishing, confirm all of these:
- [ ] `lesson-N/lesson N.md` written
- [ ] `lesson-N/homework N.md` written
- [ ] `session-N.html` built (matches previous session template)
- [ ] Highlight clips extracted + thumbnails generated
- [ ] Clips embedded in session page
- [ ] `index.html` updated (session status + cheat sheet)
- [ ] `CONTEXT.md` updated
- [ ] Committed, pushed, deployed, and aliased
