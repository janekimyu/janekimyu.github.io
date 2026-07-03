# Retro Homepage Variations Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build three complete playful personal GitHub Pages homepage variations and a new selector homepage that links to them.

**Architecture:** Keep the site dependency-free and static. Each variation is a self-contained HTML file with embedded CSS and JavaScript so GitHub Pages can serve it directly and each page can maintain a distinct visual system.

**Tech Stack:** Static HTML5, CSS3, vanilla JavaScript, local `python3 -m http.server` verification, browser viewport checks.

## Global Constraints

- Replace the current experimental homepage with a personal, playful GitHub Pages site about Jane, coding, websites, AI, and making strange little internet things.
- Create `index.html`, `jane-exe.html`, `desktop.html`, and `bbs.html`.
- Do not link existing experimental pages from the new homepage.
- Keep existing experimental pages untouched.
- Use static HTML/CSS/JavaScript suitable for GitHub Pages.
- Keep the code dependency-free.
- Favor semantic markup, responsive layouts, accessible link/button labels, keyboard-friendly interactions, and `prefers-reduced-motion` support.
- Confirm no mobile horizontal overflow.

---

## File Structure

- Modify `index.html`: replace the current room list with a retro selector page that introduces and links the three variations.
- Create `jane-exe.html`: CRT terminal homepage with boot rhythm, command navigation, five content sections, and reduced-motion support.
- Create `desktop.html`: fake desktop homepage with interactive icons, focusable/closable windows, a taskbar, and mobile stacked layout.
- Create `bbs.html`: old-web BBS shrine homepage with fake connection header, ASCII menu, readable sections, badges, and guestbook-style contact.
- Do not modify `breathe.html`, `blessing.html`, `sky.html`, `veranda.html`, or `oracle.html`.

---

### Task 1: Main Selector Homepage

**Files:**
- Modify: `index.html`

**Interfaces:**
- Consumes: No new local files are required before this task.
- Produces: Three ordinary links: `jane-exe.html`, `desktop.html`, and `bbs.html`.

- [x] **Step 1: Replace `index.html` with a selector page**

Use a complete static document with:

- `<title>jane's weird computer</title>`
- Three prominent links to `jane-exe.html`, `desktop.html`, and `bbs.html`
- No links to `breathe.html`, `blessing.html`, `sky.html`, `veranda.html`, or `oracle.html`
- Responsive CSS with no external dependencies
- A playful retro-computer frame and copy about coding, websites, AI, and internet experiments

- [x] **Step 2: Check links and forbidden old-room links**

Run:

```bash
rg -n "jane-exe.html|desktop.html|bbs.html|breathe.html|blessing.html|sky.html|veranda.html|oracle.html" index.html
```

Expected: output includes the three new variation links and no old-room page links.

---

### Task 2: JANE.EXE Terminal Page

**Files:**
- Create: `jane-exe.html`

**Interfaces:**
- Consumes: `index.html` links to `jane-exe.html`.
- Produces: A self-contained page with section ids `about`, `web`, `ai`, `projects`, and `contact`.

- [x] **Step 1: Create the page**

Use a complete static document with:

- `<title>JANE.EXE</title>`
- A visible home link back to `index.html`
- A CRT terminal shell with scanlines, glow, and a boot log
- Command buttons or links for `ABOUT`, `WEB`, `AI`, `PROJECTS`, and `CONTACT`
- Sections with ids `about`, `web`, `ai`, `projects`, and `contact`
- Three project slots for experiments, drafts, and internet things in progress
- JavaScript that reveals the boot log progressively unless reduced motion is enabled
- Keyboard-focus styles for all interactive controls

- [x] **Step 2: Check required section ids and home link**

Run:

```bash
rg -n "id=\"about\"|id=\"web\"|id=\"ai\"|id=\"projects\"|id=\"contact\"|href=\"index.html\"" jane-exe.html
```

Expected: all five section ids and the home link are present.

---

### Task 3: Desktop From Another Timeline Page

**Files:**
- Create: `desktop.html`

**Interfaces:**
- Consumes: `index.html` links to `desktop.html`.
- Produces: A self-contained page with window buttons using `data-window` ids: `about`, `web`, `ai`, and `links`.

- [x] **Step 1: Create the page**

Use a complete static document with:

- `<title>desktop from another timeline</title>`
- A visible home link back to `index.html`
- Desktop icons for `About Me`, `Web Stuff`, `AI Experiments`, and `Links`
- Four windows with matching ids `window-about`, `window-web`, `window-ai`, and `window-links`
- Close buttons for each window
- JavaScript that opens, focuses, and closes windows
- A taskbar or menu area
- A mobile layout where windows stack in one column and remain readable
- Keyboard-focus styles for icons and window controls

- [x] **Step 2: Check window hooks**

Run:

```bash
rg -n "data-window=\"about\"|data-window=\"web\"|data-window=\"ai\"|data-window=\"links\"|window-about|window-web|window-ai|window-links" desktop.html
```

Expected: all four icon hooks and all four window ids are present.

---

### Task 4: Personal BBS / Web Shrine Page

**Files:**
- Create: `bbs.html`

**Interfaces:**
- Consumes: `index.html` links to `bbs.html`.
- Produces: A self-contained page with section ids `login`, `menu`, `notes`, `links`, and `guestbook`.

- [x] **Step 1: Create the page**

Use a complete static document with:

- `<title>jane's tiny bbs</title>`
- A visible home link back to `index.html`
- A fake connection / login header
- ASCII-style menu links
- Notes about coding, AI, websites, experiments, and making things for fun
- A tiny links or badges area
- A guestbook-style contact block
- Lightweight blinking/status animation with a reduced-motion fallback
- Mobile CSS that wraps ASCII decorations instead of causing horizontal overflow

- [x] **Step 2: Check required section ids and menu anchors**

Run:

```bash
rg -n "id=\"login\"|id=\"menu\"|id=\"notes\"|id=\"links\"|id=\"guestbook\"|href=\"#notes\"|href=\"#guestbook\"" bbs.html
```

Expected: all required ids and key menu anchors are present.

---

### Task 5: Local Browser Verification

**Files:**
- Verify: `index.html`
- Verify: `jane-exe.html`
- Verify: `desktop.html`
- Verify: `bbs.html`

**Interfaces:**
- Consumes: all four implemented pages.
- Produces: verified static pages ready for GitHub Pages.

- [x] **Step 1: Start a local static server**

Run:

```bash
python3 -m http.server 4173
```

Expected: server starts at `http://localhost:4173/`.

- [x] **Step 2: Verify navigation**

Open `http://localhost:4173/` and click all three variation links.

Expected:

- `JANE.EXE` loads at `/jane-exe.html`
- `Desktop From Another Timeline` loads at `/desktop.html`
- `Personal BBS / Web Shrine` loads at `/bbs.html`
- Each variation includes a working home link back to `/index.html`

- [x] **Step 3: Verify core interactions**

In `jane-exe.html`, click each command button and confirm it scrolls to or focuses the matching section.

In `desktop.html`, click each desktop icon, confirm the matching window appears/focuses, then close it.

In `bbs.html`, click menu anchors and confirm they navigate to the matching sections.

- [x] **Step 4: Verify responsive behavior**

Check at desktop width and a mobile width near `390px`.

Expected:

- No horizontal overflow on any page
- Text stays inside its visual containers
- Desktop windows stack cleanly on mobile
- ASCII decorations on `bbs.html` wrap or shrink without forcing sideways scroll

- [x] **Step 5: Check untouched experimental files**

Run:

```bash
git diff -- breathe.html blessing.html sky.html veranda.html oracle.html
```

Expected: no output.

- [x] **Step 6: Commit implementation**

Run:

```bash
git add index.html jane-exe.html desktop.html bbs.html docs/superpowers/plans/2026-07-03-retro-homepage-variations.md
git commit -m "feat: Add retro homepage variations" -m "Build three playful static homepage variations for GitHub Pages and a selector homepage that links them together." -m "Co-Authored-By: GPT-5 Codex <noreply@openai.com>"
```
