# Interactive Pin-Tumbler Lock Cross-Section

An interactive, self-contained explainer that shows **how a key actually works** inside a pin-tumbler lock: the five pin stacks, the shear line, and why only the right key turns the plug.

**Try it:** open `index.html` (works offline — no server, no API keys, no network).
Dark theme: `lock-dark.html`.

## What it shows

- **Correct key** — all 5 pin stacks line up at the shear line; the end-face indicator rotates to 70°.
- **Wrong key** — only 3 of 5 line up, so the plug stays blocked.
- **Partially inserted key** — handled as its own case; drag or use the arrow keys to change insertion depth.
- **Click any pin** to read why it is, or is not, aligned.
- **Housing toggle** switches between the exterior and the cross-section.
- Keyboard controls (1 / 2 / Enter / Escape / ←→), reduced-motion support, light and dark themes, 390 px phone layout.

## How it was made

1. Installed the open-source **Anatomy** skill (`github.com/wheresryan22/anatomy`, MIT) into an AI coding agent.
2. Wrote the brief: an interactive pin-tumbler cross-section with the interactions listed above.
3. The agent produced the build scripts, the page, and its own browser checks.
4. I reviewed the published page by hand; the agent also ran its own browser checks. Both are listed below under "What was checked".

I did not write the rendering library. My part is the brief, the review, and the decision about what is safe to publish.

## What was checked

**Reviewed by me, by hand, on the published page**

- Correct key: 5 / 5 pin stacks aligned, and turning moves the end-face indicator to 70°.
- Wrong key: 3 / 5 aligned, and turning is blocked.
- Clicking each pin: the explanation matches what is on screen.
- Housing toggle between the exterior and the cross-section.
- 390 px phone width.
- Dark theme (`lock-dark.html`).

**Run by the agent (automated browser checks)**

- Interaction paths: correct key, wrong key, partially inserted key, turning, housing toggle, mouse and keyboard.
- Both themes, reduced-motion preference, 390 px phone width, and the browser console.
- A geometry audit of **52 recorded parts** in their starting pose: support, intersections, drawing order.
- Screenshots of each state (`shots/`).

Keyboard controls, reduced-motion behaviour, the partially inserted key and the browser console were covered by the agent's checks only, not by my manual pass.

## Limits (stated on purpose)

- The geometry audit covers the **starting pose only**. This is not a full mechanical simulation; moving parts were checked through model assertions and browser interaction, not physics.
- Tooth positions and pin lengths are **illustrative drawing units** — not the dimensions of any real key or lock.
- This is a **teaching diagram**. It is not a security analysis and not a guide to picking real locks.

## For real client products

A diagram like this is only as accurate as its inputs. For a real product I would need the spec sheet or CAD, agree which dimensions are exact and which are schematic, and have someone on the client side sign off before anything is published.

## Credits & license

- Mechanism reference: ASSA ABLOY *Master Keying System Design Guide* (linked in the page).
- Rendering kit and check scripts: [wheresryan22/anatomy](https://github.com/wheresryan22/anatomy), MIT — license and copyright notice retained in `LICENSE-anatomy`.
- Everything in this repository is provided as a sample/demonstration.
