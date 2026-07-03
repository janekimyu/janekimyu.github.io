# Retro Homepage Variations Design

## Goal

Replace the current experimental homepage with a personal, playful GitHub Pages
site about Jane, coding, websites, AI, and making strange little internet things.
The site should feel fun, unique, and intentionally different from a normal
portfolio template.

## Site Structure

- `index.html`: a main entry page that introduces the three homepage variations.
- `jane-exe.html`: a booting CRT terminal called `JANE.EXE`.
- `desktop.html`: a fake 90s desktop from another timeline.
- `bbs.html`: a personal BBS / old-web shrine.

The existing experimental pages can stay in the repo. This implementation will
not link them from the new homepage.

## Variation 1: JANE.EXE

This page should feel like an old CRT terminal booting into a personal homepage.
It should use terminal-style panels, scanlines, glowing phosphor text, and a
typed-command rhythm without requiring a real command parser.

Core sections:

- `ABOUT`: a short personal intro.
- `WEB`: notes about websites, coding, and making small internet things.
- `AI`: playful copy about AI experiments and tools.
- `PROJECTS`: three honest project slots for experiments, drafts, and internet
  things in progress.
- `CONTACT`: simple links or text for reaching Jane.

Expected interactions:

- A brief boot sequence or typed intro.
- Clickable command buttons that jump to sections.
- A blinking cursor and subtle CRT effects.
- Reduced-motion fallback that shows the content without boot animation.

## Variation 2: Desktop From Another Timeline

This page should feel like opening a strange old operating system. It should be
playful and personal, not a corporate portfolio dressed as an OS.

Core windows:

- `About Me`
- `Web Stuff`
- `AI Experiments`
- `Links`

Expected interactions:

- Windows can be opened from desktop icons.
- Windows can be focused and closed.
- A simple taskbar or menu area makes the page feel like a complete desktop.
- On mobile, windows stack into a readable single-column interface.

## Variation 3: Personal BBS / Web Shrine

This page should feel like a dial-up bulletin board mixed with early personal
web energy. It can be more chaotic than the other two, but the text still needs
to be readable.

Core sections:

- A fake connection / login header.
- ASCII-style menu items.
- Personal notes about coding, AI, websites, and experiments.
- A tiny links/badges area.
- A guestbook-style contact block.

Expected interactions:

- Blink/cursor details and small hover states.
- Menu links jump to sections.
- Decorative status lights or connection text can animate lightly.
- Mobile layout keeps ASCII decorations from causing horizontal overflow.

## Visual Direction

Use three related but distinct retro modes:

- `JANE.EXE`: black screen, green or amber glow, terminal geometry.
- `Desktop`: gray chrome, pixel-ish buttons, window shadows, soft desktop color.
- `BBS`: dark navy or black base, cyan/magenta/yellow accents, ASCII borders.

The pages should share enough language to feel like one personal site, but each
variation should have its own mood. Avoid a generic portfolio look.

## Content Tone

The copy should sound casual, playful, and human. It can mention coding,
websites, AI, experiments, internet rooms, and making things for fun. It should
not over-explain the UI or read like marketing copy.

## Implementation Notes

Build as static HTML/CSS/JavaScript suitable for GitHub Pages. Keep the code
dependency-free unless a clear need appears. Favor semantic markup, responsive
layouts, accessible link/button labels, keyboard-friendly interactions, and
`prefers-reduced-motion` support.

## Verification

Before completion:

- Open the site locally in a browser.
- Check desktop and mobile viewport behavior.
- Verify the three variation pages load from `index.html`.
- Verify core interactions on each page.
- Confirm no mobile horizontal overflow.
- Confirm existing experimental pages remain untouched and unlinked from the new
  homepage.
