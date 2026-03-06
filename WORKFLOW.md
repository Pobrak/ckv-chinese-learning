# 📋 CKV Lesson Generation Workflow

> **Version**: 1.0 | **Established**: 06 March 2026  
> This document defines how new learning sessions are planned, vetted, and generated.

---

## Overview

Lessons are generated in **two stages** to give the parent/supervisor full control over content before any HTML is built.

```
Stage 1: LESSON PLAN (plain text)
   └── 陈老师 pulls latest session log from GitHub
   └── Drafts lesson plan: content + UI spec
   └── Parent reviews → edits via Claude reply → or approves

Stage 2: HTML GENERATION
   └── Only triggered by parent approval
   └── 陈老师 builds the interactive session
   └── Session log generated at end of session
   └── Log pushed to GitHub
```

---

## Stage 1: Lesson Plan Draft

### What triggers it
- Parent says "generate next session" or similar
- 陈老师 automatically pulls the most recent session log from GitHub
- No manual data pasting required

### What the plan contains

```
LESSON PLAN — Session [N]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

SESSION CONTEXT (pulled from last log)
  - Last session: date, topic, scores
  - Kumon drill queue: characters needing repetition
  - Weak areas: specific items that scored low
  - Effort/emotional state from last session

LESSON RATIONALE
  - Why these characters/topics were chosen
  - How this responds to last session's gaps
  - Progression logic (remediation vs. new content)

CHARACTER LIST
  - 识读字 to introduce or drill (with pinyin + meaning)
  - 识写字 to practise writing (with stroke note if complex)
  - Explicitly marked: REVIEW vs. NEW

SENTENCE PATTERNS
  - Patterns to introduce or reinforce
  - Example sentences using CKV's interests

ACTIVITY BREAKDOWN
  - Each section listed with:
    - Name & purpose
    - Duration (minutes)
    - Interaction type (e.g. tap, drag, type, write on paper, oral)
    - UI elements required (buttons, flashcards, matching grid,
      fill-in-blank, sentence builder, free canvas, audio cue, etc.)
    - Difficulty level (warm-up / core / stretch)

ENGAGEMENT HOOKS
  - Which Pokémon/Minecraft/PE/food/Kang Yai moments are woven in

REAL LIFE MISSION (proposed)
  - 2–3 items for between sessions

SESSION LOG TEMPLATE
  - Pre-filled fields based on planned content
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Stage 2: Parent Vetting

### How to respond

| Action | What to do |
|--------|-----------|
| **Approve** | Reply: "Generate" or "Looks good, go ahead" |
| **Edit a section** | Quote the section in your reply and describe the change |
| **Reject & redo** | Reply: "Scrap — [reason / new direction]" |

No special syntax needed. Just reply naturally — 陈老师 will parse it.

### What gets checked
- Are the characters appropriate for CKV's current level?
- Does the session length match energy/time available?
- Are the engagement hooks relevant to what's happening in CKV's life right now?
- Is the difficulty calibrated correctly (not too easy, not too hard)?

---

## Stage 3: HTML Generation

Triggered only after parent approval. 陈老师 builds the full interactive HTML session exactly matching the approved plan spec.

After the session runs:
1. Parent pastes the session log back into Claude
2. 陈老师 pushes the log to GitHub
3. README dashboard is updated
4. Next lesson plan will pull from this new log

---

## Progression Logic

```
IF last session scores < 60% on any activity
  → Current session: 70% review / 30% new content
  → New content held back until weak areas consolidate

IF last session scores 60–80%
  → Current session: 50% review / 50% new content
  → Normal progression pace

IF last session scores > 80%
  → Current session: 30% review / 70% new content
  → Accelerate — introduce next lesson's vocabulary early
```

*Current status (after Session 004): Blitz 4/8 (50%) · Fill-in-Blank 1/5 (20%) → REMEDIATION MODE*

---

*Living document. Update when workflow changes.*
